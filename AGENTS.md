# Idea Storage — instructions for future AI agents

This repo is the user's **personal idea archive** published as a mobile-first static website. Always follow these rules when the user asks to save an idea here.

## Canonical repository / target
- Repo: `wkdeogh/idea_storage`
- Main website: GitHub Pages from `main`, repository root (if Pages is configured).
- Site has no build step: `index.html`, `styles.css`, `app.js`, `posts/index.json`.
- Do NOT create a separate web app per idea. Every idea is a **new post** in the archive.

## Add an idea
1. Read this file and fetch the CURRENT `posts/index.json` before editing. Do not overwrite existing posts or other files.
2. Add one object to the JSON array with:
   - `id`: unique date + slug, e.g. `2026-11-02-my-new-idea`
   - `slug`: unique lowercase hyphenated ASCII slug (stable URL identifier)
   - `date`: ISO YYYY-MM-DD, Korea timezone if dates matter
   - `category`, `title`, `subtitle`, `summary`, `tags` (array)
   - `thesis`: one-sentence core idea
   - `sections`: array of `{heading, paragraphs?: string[], bullets?: string[], quote?: string}`
   - optional `video`: `{title, logline, scenes:[{time,title,narration,visual}], checklist:string[]}`
   - optional `questions`: string[]
3. Preserve the user's thought progression and distinguish original hypothesis, amendments, counterarguments and uncertainties. Do not describe speculation as established evidence. Preserve the user's voice without amplifying unfounded claims.
4. Make each entry a reusable, self-contained long-form article. When appropriate, include a ready-to-adapt YouTube video outline with scenes and visuals.
5. Keep valid UTF-8 JSON; verify with a JSON parser if available. Do not introduce a trailing comma.
6. Post URLs are `https://wkdeogh.github.io/idea_storage/?post=<slug>`. URL changes break existing links, so keep slugs stable.
7. Ensure home search, tags, and mobile rendering still work. No new routing needed, no package install or build required.
8. Commit to `main`, verify GitHub contents and Pages status if available, and share a link to the new post.

## Edit an existing idea
- Update the matching object by slug; do not duplicate it.
- Preserve its original date unless user requests otherwise; optionally add an updated date field.
- Avoid changing unrelated posts.
- This site contains public content if repository is public: warn before saving sensitive information.

## Architecture
- `app.js` fetches `./posts/index.json`, renders a responsive list and individual posts via `?post=slug`.
- All text is inserted with `textContent` or HTML-escaped in cards. Keep safe rendering, no untrusted raw HTML.
- Mobile first, no dependencies or backend, GitHub Pages compatible.
- If expanding features, retain backward compatibility with existing post JSON.

## Validation before completion
- Confirm all required fields and uniqueness of `id` and `slug`.
- Verify JSON parses, all scene items have required fields if video exists, all sections contain a heading.
- Check links using repository-relative URLs, including project pages.
- If GitHub Pages is not enabled, give exact user-facing steps rather than falsely claiming deployed.
