---
name: obsidian-build-bilingual-technical-english-notes
description: >-
  Convert English technical articles, engineering blogs, and documentation into bilingual Chinese-English Obsidian study notes for technical understanding and language learning. Preserve the original structure and images, add paragraph-level collapsible Vocabulary and Technical Notes callouts, explain difficult words and technical concepts in Simplified Chinese, and create end-of-note glossaries, architecture summaries, concept comparisons, and review questions. Use when the user asks to save, annotate, or study a technical article in Obsidian, especially for 技术英语精读、双语技术笔记、生词标注、专业术语学习、技术概念讲解, or bilingual technical language learning.
---

# Build Bilingual Technical English Notes

Turn an English technical source into an Obsidian note that supports two goals at once: learning the source language and understanding the technology. Keep the English source readable; place Chinese learning aids in foldable callouts.

## Choose the Workflow

- **Import and annotate a URL:** Extract the article, download meaningful images, create the Obsidian note, then annotate it.
- **Annotate an existing note:** Preserve its metadata, prose, headings, links, code, tables, and images; add only the learning layer.
- **Create a sample:** When the user asks for a trial, annotate the requested section or first three natural paragraphs and stop for feedback.
- **Extend a sample to the full text:** Reuse the accepted style exactly and cover all remaining technical prose.

Infer a reasonable target note and attachment directory from the vault. Ask only when multiple existing targets would make an unsafe overwrite likely.

## 1. Acquire and Preserve the Source

1. Prefer a clean article extractor for public web pages. Fall back to browser or web-page inspection when extraction is blocked or incomplete.
2. Capture title, canonical URL, publication date, authors, headings, prose, lists, tables, code, captions, and meaningful article images.
3. Exclude navigation, cookie banners, related-article cards, application badges, and other page chrome.
4. Download the cover and in-article figures into a note-specific attachment directory. Use stable descriptive filenames such as `00-cover.png` and `figure-01.png`.
5. Replace remote image references with Obsidian embeds. Keep the source URL in frontmatter and in a visible source callout.
6. Preserve the original English wording and paragraph order. Do not silently translate, summarize, or rewrite the source.

When a source blocks automated extraction, change the retrieval method rather than inventing missing content. Record uncertainty if any section cannot be verified.

## 2. Build the Base Obsidian Note

Create valid Obsidian Flavored Markdown with:

- YAML properties for `title`, `source`, `published`, `imported`, `authors`, and relevant tags;
- one H1 title;
- a visible source callout;
- the local cover image when available;
- the complete source structure and local figure embeds.

Use wikilink embeds for vault-local media and ordinary Markdown links for external sources. Do not break prose into screen-width lines; treat natural paragraphs and cohesive lists as learning units.

## 3. Add the Language-Learning Layer

After each substantive prose unit, add a collapsed callout:

```markdown
> [!note]- Vocabulary｜词汇
> - **term or phrase** *part of speech*：简体中文语境释义；必要时说明搭配、语气或与近义词的差别。
```

Select words and phrases that are valuable to an intermediate Chinese-speaking technical learner:

- difficult general academic vocabulary;
- common engineering collocations and phrasal expressions;
- domain terminology and abbreviations;
- words whose contextual meaning differs from their everyday meaning.

Explain meaning in context, not as an indiscriminate dictionary dump. Include parts of speech when useful. Preserve the English term and use Simplified Chinese for explanations. Avoid repeating already-mastered terms in every paragraph; reinforce them only when the new context adds meaning.

## 4. Add the Technical-Learning Layer

Immediately after the vocabulary callout, add:

```markdown
> [!tip]- Technical Notes｜技术理解
> - 用简体中文解释本段的技术机制、组件职责或工程取舍。
> - 必要时区分相近概念，并连接到全文架构。
```

Make technical notes educational rather than merely translational:

- explain what the mechanism does and why it exists;
- connect components, identities, data flows, and trust boundaries;
- distinguish commonly confused concepts;
- interpret metrics carefully, including percentile and scope caveats;
- separate implemented architecture from future plans;
- label source-based inference as inference and avoid unsupported claims.

Group a numbered procedure, feature list, or tightly coupled bullet list into one learning unit. Do not add redundant callouts after pure figure captions, trademarks, social links, or short author-role labels. Annotate author biographies only when the user asks.

## 5. Create the End-of-Note Review

Append a clearly separated `## 全文学习汇总` after the source content. Include the items that materially aid review:

1. a one-sentence Chinese thesis;
2. a compact Mermaid flowchart when three or more components or hops interact;
3. a deduplicated core vocabulary glossary;
4. a comparison table for easily confused concepts;
5. a component-responsibility table for architecture-heavy articles;
6. a concise process, layered model, or mental model;
7. metric interpretation caveats when the article presents performance data;
8. five to ten retrieval-practice questions;
9. one final memory chain in a collapsed or highlighted callout.

Read [references/output-patterns.md](references/output-patterns.md) when creating or auditing the note structure.

## 6. Verify Before Handoff

Check all of the following:

- the original English article remains complete and in order;
- every meaningful remote image has a local file and valid embed;
- no local embed points to a missing file;
- Vocabulary and Technical Notes callouts are paired for each substantive learning unit;
- callouts are collapsed by default and render as Obsidian callouts;
- code fences, tables, lists, links, captions, and Mermaid fences remain valid;
- the glossary is deduplicated and terminology is consistent;
- technical explanations do not overstate the source;
- UTF-8 Chinese text renders without mojibake;
- the final note remains readable when all callouts are collapsed.

Report the note path, attachment count, annotation-pair count, and validation result. Do not claim visual or link verification unless it was actually performed.
