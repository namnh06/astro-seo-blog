# Standalone Astro Template

Use this template when `astro_structure.type` is `standalone` in BLOG_CONFIG.yaml.

**File location:** `src/pages/blog/[slug].astro`

---

## Template

```astro
---
import BlogLayout from '../../layouts/BlogLayout.astro';
import TableOfContents from '../../components/TableOfContents.astro';

// REQUIRED: Export metadata for blog index page
export const metadata = {
  title: "[Blog Post Title - without site name]",
  slug: "[url-slug-matching-filename]",
  description: "[Meta description 150-160 chars]",
  date: "YYYY-MM-DDTHH:MM:SS[timezone]",
  category: "[Category from config options]",
  readingTime: "[X] min read",
};

const headings = [
  { id: 'first-section-slug', text: 'First Section Title', level: 2 },
  { id: 'second-section-slug', text: 'Second Section Title', level: 2 },
  { id: 'third-section-slug', text: 'Third Section Title', level: 2 },
  { id: 'professional-help', text: 'Professional Help Section', level: 2 },
  { id: 'related-articles', text: 'Related Articles', level: 2 },
];
---

<BlogLayout
  title="[Blog Post Title] | [Business Name]"
  description="[Meta description 150-160 chars]"
  publishedTime="YYYY-MM-DDTHH:MM:SS[timezone]"
  category="[Category]"
  readingTime="[X] min read"
  slug="[url-slug]"
  author="[Author Name]"
>
  <h1 slot="title">[Blog Post Title]</h1>

  <TableOfContents headings={headings} slot="toc" />

  <!-- Opening Section -->
  <p>
    [Engaging opening paragraph. Address reader's pain point.
    Mention location naturally. Include primary keyword.]
  </p>

  <p>
    [Second paragraph establishing expertise. What will they learn?
    Early link to <a href="/">Business Name</a> or service page.]
  </p>

  <blockquote>
    [Key statistic or important insight]
  </blockquote>

  <h2 id="first-section-slug">First Section Title</h2>

  <p>
    [Content providing actionable information. 150-300 words.]
  </p>

  <h3>Subsection if Needed</h3>

  <ul>
    <li><strong>Point 1:</strong> Explanation</li>
    <li><strong>Point 2:</strong> Explanation</li>
    <li><strong>Point 3:</strong> Explanation</li>
  </ul>

  <h2 id="second-section-slug">Second Section Title</h2>

  <p>
    [More valuable content. Include internal link to
    <a href="/blog/related-post">related blog post</a>.]
  </p>

  <h2 id="third-section-slug">Third Section Title</h2>

  <p>
    [Continue providing value. Mention location again naturally.]
  </p>

  <h2 id="professional-help">[CTA Heading from config]</h2>

  <p>
    [CTA intro from config. Link to <a href="/">Business Name</a> and
    <a href="/services/primary-service">primary service</a>.]
  </p>

  <p>Our service includes:</p>

  <ul>
    <li><strong>Benefit 1</strong> - description</li>
    <li><strong>Benefit 2</strong> - description</li>
    <li><strong>Benefit 3</strong> - description</li>
    <li><strong>Local [Location] team</strong> - description</li>
  </ul>

  <p>
    [Closing CTA] - <a href="/contact">contact us today</a> for a free consultation!
  </p>

  <h2 id="related-articles">Related Articles</h2>

  <ul>
    <li><a href="/blog/post-1">Related Post 1</a> - Brief 10-15 word description</li>
    <li><a href="/blog/post-2">Related Post 2</a> - Brief description</li>
    <li><a href="/blog/post-3">Related Post 3</a> - Brief description</li>
  </ul>
</BlogLayout>
```

---

## Field Reference

### Metadata Object (Required)

| Field | Required | Format | Notes |
|-------|----------|--------|-------|
| title | Yes | String | Without site name suffix |
| slug | Yes | String | Must match filename |
| description | Yes | String | 150-160 chars |
| date | Yes | ISO with timezone | `YYYY-MM-DDTHH:MM:SS-06:00` |
| category | Yes | String | From config options |
| readingTime | Yes | String | e.g., "7 min read" |

### BlogLayout Props

All props should match the metadata values, with:
- `title` includes site name: `"Post Title | Business Name"`
- `publishedTime` same as `date`
- `author` from config

### Headings Array

- Each H2 needs a matching entry in headings array
- `id` must match the H2's `id` attribute exactly
- `level` is always `2` for H2 sections

### Date Format with Timezone

**CRITICAL**: Standalone Astro files need timezone offset.

- Check `timezone` in BLOG_CONFIG.yaml (e.g., `-06:00` for Saskatchewan)
- Format: `"2026-01-25T12:00:00-06:00"`
- Without timezone, dates display incorrectly due to UTC conversion
