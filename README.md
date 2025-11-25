# .github

## 프롬프트

```
📝 Claude Skills 활용 프롬프트 작성 방법

1️⃣ 직접적인 방법 (명시적으로 스킬 호출)
"
mcp-builder 스킬을 사용해서 README.md의 설계 문서대로 MCP 서버를 개발해줘
기술 스택을 사용하기 전에 Context7 MCP를 사용해서 최신 기술 사용 방법을 확이하고 나서 개발을 진행해줘.
"
또는
"
mcp-builder 스킬로 Legacy Code Archive MCP Server를 구현해줘
"

2️⃣ 자연어 방법 (스킬 목적과 일치하는 요청)
스킬의 description이 "MCP 서버를 생성하기 위한 가이드"이므로, 자연스럽게:
"
README.md에 있는 설계대로 FastMCP를 사용해서 MCP 서버를 만들어줘
"
또는
"
이 프로젝트를 MCP 서버로 구현해줘. Python FastMCP 사용하고, 
설계 문서에 나온 대로 index_codebase와 search_legacy_code 도구를 만들어야 해
"

3️⃣ 추천 프롬프트 (현재 프로젝트에 최적화)
"
mcp-builder 스킬을 사용해서 개발해줘.

README.md에 정의된 설계 문서를 따라서:
1. FastMCP 프레임워크로 MCP 서버 구현
2. index_codebase 도구 - 코드베이스 인덱싱
3. search_legacy_code 도구 - 시맨틱 검색
4. LanceDB + OpenAI Embedding 사용
5. Java, Vue.js, TypeScript 지원
"

💡 핵심 팁
스킬 이름 명시: mcp-builder 스킬을 사용해서 또는 mcp-builder로
구체적인 요구사항 포함: 설계 문서의 어떤 부분을 구현할지 명시
기술 스택 언급: FastMCP, Python, TypeScript 등
```
