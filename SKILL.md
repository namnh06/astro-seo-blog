---
name: astro-seo-blog
description: Write an SEO-optimized blog post for any Astro website. Use when the user wants to create a new blog post, write content for the blog, or mentions "blog post," "SEO content," "write article," or "create blog." Reads BLOG_CONFIG.yaml from project root for business-specific settings and applies universal Google Search Central best practices.
argument-hint: "[topic]"
---

# Write SEO-Optimized Astro Blog Post

Write an SEO-optimized blog post about **$ARGUMENTS** for an Astro website.

## Workflow

1. Read `BLOG_CONFIG.yaml` in the project root
2. Scan the blog directory to avoid duplicate topics and find related posts
3. Apply SEO best practices from [seo-guidelines.md](seo-guidelines.md)
4. Use the appropriate template from [templates/](templates/)
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

If no config exists, ask the user to create one from [blog-config-template.yaml](blog-config-template.yaml).

## Additional Resources

- For complete SEO guidelines, see [seo-guidelines.md](seo-guidelines.md)
- For Astro file templates, see [templates/](templates/)
- For example output, see [examples/](examples/)

## Date Format

**CRITICAL**: Check the system date before setting `pubDate`.

- Content Collections: `YYYY-MM-DD`
- Standalone Astro: `YYYY-MM-DDTHH:MM:SS[timezone]` (timezone from config)
