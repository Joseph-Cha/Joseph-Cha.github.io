# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based blog hosted on GitHub Pages, primarily focused on "Today I Learned" (TIL) posts about Flutter, Dart, Figma, and other development topics. The blog uses the Minimal Mistakes theme and is written in Korean.

**Site Information:**
- URL: https://joseph-cha.github.io/blog
- Theme: Minimal Mistakes (remote theme v4.22.0)
- Locale: ko-KR (Korean)
- Baseurl: `/blog`

## Commands

### Development
```bash
# Install dependencies
bundle install

# Build the site locally
bundle exec jekyll build

# Serve the site locally (with auto-rebuild)
bundle exec jekyll serve

# Build with production baseurl
bundle exec jekyll build --baseurl "/blog"
```

### Deployment

The site automatically deploys to GitHub Pages via GitHub Actions when changes are pushed to the `main` branch. The workflow is defined in `.github/workflows/jekyll.yml` and uses Ruby 3.1.4.

## Content Structure

### Blog Posts (`_posts/`)

All blog posts follow a strict naming convention and structure:

**File Naming:**
- Format: `YYYY-MM-DD-TIL-YY.MM.DD(topic-N).md`
- Example: `2025-10-15-TIL-25.10.15(figma-1).md`

**Post Structure:**

Every TIL post must follow this template:

```markdown
---
title: "Today I Learned N회차 - [Topic]"
date: YYYY-MM-DDTHH:MM:SS-00:00
categories:
  - TIL
tags:
  - TIL
  - [TopicTag1]
  - [TopicTag2]
---

[한글로 작성된 서론 - 오늘 배운 내용 요약]

## 🎯 학습 목표

- [학습 목표 1]
- [학습 목표 2]

## 📚 학습 내용

### 1. [주제 1]

[내용을 표, 코드 블록, 계층 구조 등으로 시각적으로 정리]

## 💡 핵심 개념 정리

[트리 구조나 표로 핵심 내용 요약]

## 💻 [코드 예시 또는 유용한 팁 정리]

## 🚀 다음 학습 목표

1. **[주제]**: [설명]
```

**Key Formatting Guidelines:**
- Use emoji section headers: 🎯 (목표), 📚 (내용), 💡 (정리), 💻 (코드/팁), 🚀 (다음 목표)
- Include both `TIL` category and topic-specific tags
- Use tables for comparing features or listing properties
- Use code fences with language specifiers for code examples
- Use tree structures (with `└─`, `├─`, `│`) to visualize hierarchies
- Write all content in Korean with a friendly, educational tone

### Pages (`_pages/`)

Static pages for archives:
- `category-archive.md` - Categories listing
- `tag-archive.md` - Tags listing
- `year-archive.md` - Chronological listing

## Configuration

### Jekyll Configuration (`_config.yml`)

Key settings that affect content generation:
- **Permalink structure**: `/:categories/:title/`
- **Pagination**: 5 posts per page
- **Markdown processor**: kramdown with GFM input
- **Comments**: Disqus (shortname: "joseph-cha")
- **Default post layout**: single with author profile, read time, comments, share, and related posts enabled

### Front Matter Defaults

All posts automatically inherit:
```yaml
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
```

## Content Guidelines

When creating or modifying TIL posts:

1. **Consistency**: Follow the established structure and emoji usage exactly
2. **Visual Organization**: Use tables, tree structures, and code blocks liberally
3. **Korean Language**: All content should be in Korean, with a friendly "익혔어요!" tone
4. **Technical Accuracy**: Ensure technical terms are accurate even in Korean
5. **Examples**: Include practical code examples with syntax highlighting
6. **Progressive Learning**: Each post should reference "다음 학습 목표"

### Blog Post Review Guidelines

When the user requests a blog post review or asks to modify a post according to guidelines, **always reference and apply the comprehensive style guide** located at:

**`.claude/BLOG_STYLE_GUIDE.md`**

This style guide includes:
- **Enhanced title format** with emoji bookends: `"📚 Today I Learned X회차 - [주제] 💡"`
- **Detailed section structure** with specific emoji usage per section type
- **Text styling rules**: bold for key concepts, backticks for code/terms, colors for emphasis
- **Code block requirements**: language specification and comprehensive comments
- **Image formatting**: center alignment, appropriate sizing, descriptions
- **Comprehensive checklists** for post completion and review

**Key differences from basic template:**
- Titles should have both opening (📚) and closing (💡 or topic-relevant) emojis
- More liberal use of emojis in section headers with specific semantic meanings
- Enhanced visual styling with colors and highlights
- More detailed code comments
- Structured closing sections: "✅ 오늘 배운 것" and "🚀 다음 계획"

When reviewing posts, ensure all items in the style guide checklists are satisfied.

## Git Workflow

- Main branch: `main`
- Commit messages typically follow pattern: `#TIL: YY.MM.DD 작성 ([Topic])`
- GitHub Actions handles deployment automatically on push to main
