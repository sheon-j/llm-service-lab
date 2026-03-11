# UV 가이드

| 공식 문서                                                 |
| -------------------------------------------------------- |
| [https://docs.astral.sh/uv/](https://docs.astral.sh/uv/) |

`uv`는 Python 패키지 관리 도구

* `pip`
* `pip-tools`
* `pyenv`
* `virtualenv`
* `poetry` 일부 기능

특징

* 매우 빠른 dependency resolver
* Python 버전 관리 가능
* 가상환경 자동 관리
* `pyproject.toml` 기반 프로젝트 관리

## 1. uv 설치

```shell
# 공식 설치 스크립트로 uv 바이너리 설치
curl -LsSf https://astral.sh/uv/install.sh | sh

# 설치 확인
uv --version

# PATH에 없다면 추가
export PATH="$HOME/.local/bin:$PATH"
```

## 2. Python / 가상환경

```shell
# Python 목록 확인
uv python list

# Python 설치
uv python install 3.12

# 현재 프로젝트에 `.venv` 생성
uv venv

# 특정 Python으로 가상환경 생성
uv venv --python 3.11

# Linux / Mac 가상환경 활성화
source .venv/bin/activate

# Windows 가상환경 활성화
.venv\Scripts\activate

# 가상환경 종료
deactivate
```

## 3. 프로젝트 초기화

```shell
# 현재 디렉토리를 uv 프로젝트로 초기화
uv init .
```

## 4. 의존성 관리

```shell
# 의존성 설치 (lock 기반)
uv sync

# 패키지 추가
uv add <패키지명>

# 패키지 삭제
uv remove <패키지명>

# 패키지 업데이트
uv upgrade <패키지명>
```

## 5. uv 환경에서 실행

```shell
# 가상환경 activate 없이 실행 가능
uv run <모듈>
```

## 6. requirements.txt 생성 (pip 호환)

```shell
# pyproject.toml → requirements.txt 변환
uv export --without-hashes > requirements.txt
```
