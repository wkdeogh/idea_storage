# ✳ 생각의 궤도 — Idea Storage

모바일 친화적인 개인 아이디어 아카이브. 아이디어를 장문 게시물로 보관하고, 유튜브 영상 기획으로 발전시키는 공간입니다.

## Website
GitHub Pages가 활성화되면: https://wkdeogh.github.io/idea_storage/

## Features
- 반응형 다크 테마 및 모바일 친화적 UI
- 아이디어 목록, 검색, 태그 필터
- 공유 가능한 상세 페이지 (?post=slug)
- 장문 아티클 및 유튜브 영상 장면별 기획 노트
- 정적 호스팅 / 빌드 불필요

## First post
[AI가 노동을 끝낸 뒤, 인류는 어디로 향할까?](https://wkdeogh.github.io/idea_storage/?post=ai-civilization-climate-space)

## Adding ideas
미래의 AI 보조자는 [AGENTS.md](./AGENTS.md)의 지침을 따라 주세요. 모든 게시물은 [posts/index.json](./posts/index.json) 배열에 들어갑니다. 기존 게시물을 유지하며 새로운 객체를 추가합니다.

## Deployment
Repo Settings → Pages → Build and deployment → Deploy from a branch → main / (root) → Save.

## Local preview
`python3 -m http.server 8000` 실행 뒤 `http://localhost:8000/` 방문.

## Visibility
현재 GitHub 저장소는 public입니다. 민감한 개인정보나 비공개 자료는 저장하지 마세요.
