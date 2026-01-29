---
name: astro-seo-blog
description: Write an SEO-optimized blog post for any Astro website. Use when the user wants to create a new blog post, write content for the blog, or mentions "blog post," "SEO content," "write article," or "create blog." Reads BLOG_CONFIG.yaml from project root for business-specific settings and applies universal Google Search Central best practices.
license: MIT
compatibility: Designed for Claude Code (or similar products)
metadata:
  author: namnh
  version: "1.0"
---

# Write SEO-Optimized Astro Blog Post

Write an SEO-optimized blog post about **$ARGUMENTS** for an Astro website.

## Workflow

1. Read `BLOG_CONFIG.yaml` in the project root
2. Scan the blog directory to avoid duplicate topics and find related posts
3. Apply SEO best practices from [references/seo-guidelines.md](references/seo-guidelines.md)
4. Use the appropriate template from [references/templates/](references/templates/)
5. Write the blog post file to the blog directory

## Quick Reference

| Requirement | Value |
|-------------|-------|
| Word count | 1,000-2,000 words |
| Internal links | 6-8 minimum |
| Location mentions | 3-5 times |
| Title length | 50-60 characters |
| Meta description | 150-160 characters |

## Configuration

The `BLOG_CONFIG.yaml` file in the project root contains:
- Business info (name, location, industry)
- Services with URLs (for internal linking)
- Target keywords
- Astro structure type (content collections vs standalone)
- CTA templates

If no config exists, ask the user to create one from [assets/blog-config-template.yaml](assets/blog-config-template.yaml).

## Critical Rules

- **Date**: Always check system date. Content Collections use `YYYY-MM-DD`; standalone uses `YYYY-MM-DDTHH:MM:SS[timezone]` (timezone from config).
- **Title**: 50-60 characters, include primary keyword and location.
- **Meta description**: 150-160 characters.
- **Word count**: 1,000-2,000 words.
- **Internal links**: 6-8 minimum (2-3 service pages, 3-4 blog posts, 1-2 homepage/contact).
- **Location mentions**: 3-5 times, naturally integrated.
- **Heading hierarchy**: Single H1, H2 for sections, H3 for subsections, never skip levels.
- **Standalone template**: Every H2 needs a matching entry in the `headings` array with exact `id` match; `title` in BlogLayout props includes site name suffix (`Post Title | Business Name`).

## Additional Resources

- For complete SEO guidelines, see [references/seo-guidelines.md](references/seo-guidelines.md)
- For Astro file templates, see [references/templates/](references/templates/)
- For example output, see [references/examples/](references/examples/)
