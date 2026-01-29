# Content Collections Template

Use this template when `astro_structure.type` is `content_collections` in BLOG_CONFIG.yaml.

**File location:** `src/content/blog/[slug].md`

---

## Template

```markdown
---
title: "[Blog Post Title - 50-60 chars]"
description: "[Meta description - 150-160 chars, compelling, includes keyword]"
pubDate: YYYY-MM-DD
author: "[Author Name from config]"
tags: ["tag1", "tag2", "[location]"]
draft: false
---

[Engaging opening paragraph that hooks the reader. Address their pain point or question immediately. Mention location naturally. Include primary keyword.]

[Second paragraph establishing expertise and what value they'll get. Link to a service page early: [service name](/services/service-slug).]

> [Key statistic or important insight as a blockquote]

## [First H2 Section - Include Keyword Variation]

[Content providing actionable information. 150-300 words. Use specific examples.]

### [Subsection if needed]

- **Point 1**: Explanation
- **Point 2**: Explanation
- **Point 3**: Explanation

## [Second H2 Section]

[More valuable content. Include internal link to related blog post: [related topic](/blog/related-post).]

## [Third H2 Section]

[Continue providing value. Mention location again naturally.]

## [Professional Help Section - Use CTA from config]

[Intro paragraph linking to primary service: [Business Name](/) and [service](/services/primary-service).]

Our service includes:

- **Benefit 1** - description
- **Benefit 2** - description
- **Benefit 3** - description
- **Benefit 4** - description
- **Local [Location] team** - description

[Closing CTA: [contact us today](/contact) for a free consultation!]

## Related Articles

- [Related Post 1](/blog/post-1) - Brief 10-15 word description
- [Related Post 2](/blog/post-2) - Brief description
- [Related Post 3](/blog/post-3) - Brief description
```

---

## Field Reference

| Field | Required | Format | Notes |
|-------|----------|--------|-------|
| title | Yes | String | 50-60 chars, no site name suffix |
| description | Yes | String | 150-160 chars |
| pubDate | Yes | YYYY-MM-DD | Today's date |
| author | No | String | From config, defaults to author.name |
| tags | No | Array | Include location tag |
| draft | No | Boolean | Set to false to publish |

## Additional Fields (site-specific)

Some sites may have additional frontmatter fields defined in their config:
- `heroImage` - Path to hero image
- `category` - Content category
- `updatedDate` - Last modified date
- Custom fields per site

Check the `frontmatter` section in BLOG_CONFIG.yaml for site-specific requirements.
