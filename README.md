# astro-seo-blog

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill that generates SEO-optimized blog posts for Astro websites. It reads your site's configuration, applies Google Search Central best practices, and writes publish-ready blog posts directly into your project.

## Usage

```
/astro-seo-blog [topic]
```

Examples:

```
/astro-seo-blog best winter home maintenance tips
/astro-seo-blog how to choose a family dentist
```

## Setup

1. **Install the skill** — Place this folder in `~/.claude/skills/astro-seo-blog/`

2. **Add a config to your project** — Copy `assets/blog-config-template.yaml` to your Astro project root as `BLOG_CONFIG.yaml` and fill in your business details, services, keywords, and Astro structure type.

3. **Run it** — Open Claude Code in your Astro project and use `/astro-seo-blog [topic]`.

## What It Does

- Reads `BLOG_CONFIG.yaml` from your project root for business-specific context
- Scans existing posts to avoid duplicate topics and find related content to link
- Detects your Astro structure (Content Collections or standalone `.astro` files)
- Applies the matching template and SEO guidelines
- Writes a complete blog post file to your configured blog directory

## SEO Standards

Each generated post follows these requirements:

| Requirement | Target |
|---|---|
| Word count | 1,000–2,000 |
| Title length | 50–60 characters |
| Meta description | 150–160 characters |
| Internal links | 6–8 minimum |
| Location mentions | 3–5 |
| Heading hierarchy | Single H1, proper H2/H3 nesting |

Content follows E-E-A-T principles (Experience, Expertise, Authoritativeness, Trustworthiness) and Google Search Central guidelines.

## Supported Astro Structures

- **Content Collections** — Markdown files in `src/content/blog/` with YAML frontmatter
- **Standalone** — `.astro` component files in `src/pages/blog/` with exported metadata and `BlogLayout` wrapper

Set `astro_structure.type` in your `BLOG_CONFIG.yaml` to `content_collections` or `standalone`.

## File Structure

```
astro-seo-blog/
├── SKILL.md                              # Skill definition and instructions
├── assets/
│   └── blog-config-template.yaml         # Template to copy into your project
└── references/
    ├── seo-guidelines.md                 # Full SEO rules and quality checklist
    ├── templates/
    │   ├── content-collections.md        # Markdown post template
    │   └── standalone-astro.md           # .astro file template
    └── examples/
        └── sample-post.md               # Example output
```

## Configuration Reference

`BLOG_CONFIG.yaml` sections:

- **business** — Name, location, industry, local references
- **author** — Name, title, credentials, bio
- **services** — Service pages with URLs and keywords (used for internal linking)
- **keywords** — Primary, secondary, and long-tail target keywords
- **pages** — Internal linking targets (homepage, contact, about, etc.)
- **astro_structure** — Structure type, blog directory, file extension, timezone
- **frontmatter** — Required/optional fields and custom fields
- **content** — Word count range, location mention targets, linking minimums
- **cta_template** — Call-to-action section template
- **existing_topics** — Previously covered topics to avoid duplication

See `assets/blog-config-template.yaml` for the full template with comments.

This skill follows the [Agent Skills](https://agentskills.io) specification.

## License

MIT
