---
title: "Personal Portfolio Website"
date: 2026-07-07
draft: false
weight: 2
categories: ["Documents"]
tags: ["Hugo", "Tailwind CSS", "GitHub Pages", "Static Site", "Markdown", "Web Development", "Personal Project"]
layout: "docs"
url: "docs/portoweb"
image: "/images/docs/portoproject.webp"
description: "Built a Hugo-based portfolio site to present data analytics case studies in one consistent format."
---

## Role

Personal Project — content structure, theme customization, and case study writing

## Problem

Data analytics project (dashboards, A/B tests, validation reports) were scattered across Looker Studio links, Google Slides decks, and PDF reports, with no single, consistent place to present them. There was no dedicated home to show the full story behind each project the problem, the approach, the reasoning, and the outcome in a format that's easy for recruiters and collaborators to skim and compare across projects.

## Solution

Built a static portfolio site using Hugo, customized from the open-source "Seven" theme and styled with Tailwind CSS, deployed as a static site through GitHub Pages. Every project is written as a structured case study in Markdown, following a shared template — Problem, Solution, Dataset/Tools, Analysis Process, Key Decisions, Key Insights, and Recommendations, so any project can be read the same way regardless of its subject matter.

## Tech Stack

| **Layer** | **Technology** | **Reason** |
|---|---|---|
| Static Site Generator | Hugo | Fast builds, no runtime dependency, Markdown-first |
| Theme | Seven (customized fork) | Docs-and-blog layout suited to long-form case studies |
| Styling | Tailwind CSS | Utility-first styling, easy to restyle the theme fork |
| Hosting | GitHub Pages | Free, zero server maintenance, versioned with the repo |
| Content | Markdown | Every case study is version-controlled and portable |

## Site Structure

![Site Build & Deploy Flow](PortoWebArchitecture.svg "Figure 1: Site build & deploy flow")


- **Project (home)** — chronological list of all case studies with a one-line summary
- **Profile** — background and role information
- **Individual case study pages** — one page per project, following the shared template
- Tags and categories generated automatically from each case study's frontmatter, giving visitors a way to browse by tool or method (e.g. #Looker Studio, #A/B Testing)

## Key Decisions

- **One consistent template across every project** — every case study follows the same section order (Problem → Solution → Dataset/Tools → Process → Decisions → Insights → Recommendations), regardless of the project's topic. This makes the portfolio easy to skim and signals a repeatable way of thinking, not just a list of outputs.
- **Static site over a website builder** — Choosing Hugo over a drag-and-drop builder (Wix, Notion, etc.) keeps every case study in Markdown, version-controlled in Git, and fully portable if the theme or host ever changes.
- **A dedicated "Key Decisions" section in every write-up** — Beyond describing what was built, each project explicitly documents *why* specific analytical or methodological choices were made, since that reasoning is what's hardest to see from a dashboard screenshot alone.
- **GitHub Pages over a custom server** — A personal portfolio doesn't need server-side logic. Static hosting removes maintenance overhead entirely and keeps deployment tied directly to the Git repository.

## Outcome

- A single, consistent home for all data analytics case studies instead of scattered links across Slides, PDFs, and dashboards
- Every project follows the same readable structure, making it easy for recruiters to compare work across projects
- Zero hosting cost and no server maintenance
- Fully version-controlled — every case study revision is tracked in Git history

