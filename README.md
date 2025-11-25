# .github

## 프롬프트

```
📝 Claude Skills 활용 프롬프트 작성 방법

"
mcp-builder 스킬을 사용해서 README.md의 설계 문서대로 MCP 서버를 개발해줘.

**기술 스택 확인:**
- Context7 MCP를 사용해서 최신 기술 사용 방법을 확인하고 개발 진행

**개발 요구사항:**
- 모든 주석과 docstring은 한글로 작성
- 모든 문서(README, QUICKSTART 등)는 한글로 작성

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

**문서화 요구사항:**
- QUICKSTART.md: 
  - uvx 사용법 포함
  - uv + taskipy 개발 환경 설정 방법
  - 사용 가능한 모든 스크립트 목록
- DEPLOY.md: 
  - PyPI 배포 가이드
  - GitHub Actions 자동 배포 설정
  - uv + taskipy 개발 워크플로우 섹션
- README.md: 
  - 빠른 시작 섹션 추가
  - 📦 개발 스크립트 섹션 추가 (주요 명령어 한눈에 보기)

**테스트 요구사항:**
- 로컬에서 바로 테스트 가능한 방법 제공
- .env.example 파일 포함
- pytest 설정 및 테스트 커버리지 설정

**개발 완료 후 검증:**
- uvx로 바로 실행할 수 있는지 확인
- uv run task dev로 개발 서버 실행 가능한지 확인
- 모든 스크립트 명령어가 정상 작동하는지 확인
"

💡 핵심 팁
스킬 이름 명시: mcp-builder 스킬을 사용해서 또는 mcp-builder로
구체적인 요구사항 포함: 설계 문서의 어떤 부분을 구현할지 명시
기술 스택 언급: FastMCP, Python, TypeScript 등
```
