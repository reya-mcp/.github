# .github

## 프롬프트

```
📝 Claude Skills 활용 프롬프트 작성 방법

mcp-builder 스킬을 사용해서 README.md의 설계 문서대로 MCP 서버를 개발해줘.

**기술 스택 확인:**
- Context7 MCP를 사용해서 최신 기술 사용 방법을 확인하고 개발 진행

**개발 요구사항:**
- 모든 주석과 docstring은 한글로 작성
- 모든 문서(README, QUICKSTART 등)는 한글로 작성

**환경 변수 및 설정 관리 요구사항:**
- .env 파일이 없어도 서버가 정상적으로 import되어야 함
- 환경 변수 검증은 모듈 import 시점이 아닌, 실제 설정을 사용하는 시점(load_config 함수 호출 시)에 수행
- load_dotenv()는 모듈 레벨이 아닌 load_config() 함수 내부에서 호출하여 lazy loading 적용
- 필수 환경 변수가 없을 때 명확한 에러 메시지 제공
- 테스트 환경에서는 mock 설정으로 실행 가능하도록 설계
- Optional 환경 변수와 Required 환경 변수를 명확히 구분

**배포 요구사항:**
- uvx로 설치 없이 바로 실행 가능하도록 패키지 구조 설정
- PyPI 배포 가능한 구조로 개발 (pyproject.toml 완벽 설정)
- [project.scripts] 엔트리 포인트 설정
- 적절한 Python 패키지 네이밍 컨벤션 적용 (언더스코어)

**개발 환경 요구사항:**
- uv + taskipy를 사용한 개발 스크립트 설정
- npm run 스타일로 사용할 수 있는 명령어 제공
- pyproject.toml에 [tool.taskipy.tasks] 섹션 추가
- 필수 스크립트:
  - dev (개발 서버), test (테스트), lint (린트), format (포맷팅)
  - build (빌드), clean (정리), check (전체 검사)
  - 각 명령어에 짧은 alias 제공 (d, t, l, f 등)

**자동 배포 설정:**
- publish.yml 파일 생성
- GitHub Release 생성 시 자동으로 PyPI 배포
- workflow 내용:
  - Python 3.11 사용
  - uv run task check로 전체 검사 실행
  - python -m build로 패키지 빌드
  - twine으로 PyPI 업로드
  - PYPI_API_TOKEN secret 사용
- test.yml 파일 생성 (PR/Push 시 자동 테스트)
  - Python 3.11, 3.12 매트릭스 테스트
  - uv sync로 의존성 설치
  - uv run task check 실행

**문서화 요구사항:**
- QUICKSTART.md: 
  - uvx 사용법 포함
  - uv + taskipy 개발 환경 설정 방법
  - 사용 가능한 모든 스크립트 목록
- DEPLOY.md: 
  - PyPI 수동 배포 가이드 (단계별)
  - GitHub Actions 자동 배포 설정 방법
  - GitHub Secrets 설정 가이드
  - uv + taskipy 개발 워크플로우 섹션
  - 릴리스 생성 방법 (git tag 사용)
- README.md: 
  - 빠른 시작 섹션 추가
  - 📦 개발 스크립트 섹션 추가 (주요 명령어 한눈에 보기)
  - CI/CD 배지 추가 (GitHub Actions)

**테스트 요구사항:**
- 로컬에서 바로 테스트 가능한 방법 제공
- .env.example 파일 포함
- pytest 설정 및 테스트 커버리지 설정
- conftest.py에 테스트용 환경 변수 fixture 제공
- 환경 변수 mock 방법 문서화

**개발 완료 후 검증:**
- uvx로 바로 실행할 수 있는지 확인
- uv run task dev로 개발 서버 실행 가능한지 확인
- 모든 스크립트 명령어가 정상 작동하는지 확인
- GitHub Actions workflow 파일 문법 검증
- .env 파일 없이도 모듈 import가 정상적으로 되는지 확인

```

## PyPI 계정 설정

1. PyPI 계정 생성: https://pypi.org/account/register/
2. API 토큰 발급:
  - https://pypi.org/manage/account/token/
  - "Add API token" 클릭
  - Token name: legacy-code-archive-mcp
  - Scope: "Entire account" (첫 배포) 또는 프로젝트 선택
  - 생성된 토큰 복사 (한 번만 표시됨!)
3. GitHub Secrets 설정
  - GitHub 저장소 → Settings → Secrets and variables → Actions
  - New repository secret 클릭
  - Name: PYPI_API_TOKEN
  - Secret: PyPI API 토큰 붙여넣기

## 사용 방법

```json
{
  "mcpServers": {
    "<MCP 명칭>": {
      "command": "uvx",
      "args": ["<패키지명>"],
      "env": {
      }
    }
  }
}
```
