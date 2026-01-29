# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

This is a Claude Code skill (not a runnable codebase). It generates SEO-optimized blog posts for Astro websites. Invoked via `/astro-seo-blog [topic]`.

## Workflow

1. Read `BLOG_CONFIG.yaml` from the user's project root (if missing, prompt them to create one from `blog-config-template.yaml`)
2. Scan the blog directory to find existing posts and avoid duplicate topics
3. Determine Astro structure type from config: `content_collections` (markdown in `src/content/blog/`) or `standalone` (`.astro` files in `src/pages/blog/`)
4. Use the matching template from `templates/` and apply SEO rules from `seo-guidelines.md`
5. Write the post file to the configured blog directory

## Key Files

- `SKILL.md` — Skill definition and trigger config
- `blog-config-template.yaml` — Template users copy to their project root as `BLOG_CONFIG.yaml`
- `seo-guidelines.md` — Full SEO rules (E-E-A-T, content structure, linking strategy, quality checklist)
- `templates/content-collections.md` — Markdown blog post template (frontmatter with `pubDate: YYYY-MM-DD`)
- `templates/standalone-astro.md` — `.astro` file template (exported metadata object, headings array, `BlogLayout` wrapper, date needs timezone offset)
- `examples/sample-post.md` — Reference output showing a complete Content Collections post

## Critical Rules

- **Date**: Always check system date. Content Collections use `YYYY-MM-DD`; standalone uses `YYYY-MM-DDTHH:MM:SS[timezone]` (timezone from config).
- **Title**: 50-60 characters, include primary keyword and location
- **Meta description**: 150-160 characters
- **Word count**: 1,000-2,000 words
- **Internal links**: 6-8 minimum (2-3 service pages, 3-4 blog posts, 1-2 homepage/contact)
- **Location mentions**: 3-5 times, naturally integrated
- **Heading hierarchy**: Single H1, H2 for sections, H3 for subsections, never skip levels
- **Standalone template**: Every H2 needs a matching entry in the `headings` array with exact `id` match; `title` in BlogLayout props includes site name suffix (`Post Title | Business Name`)
