# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a single-file static personal website for Bianca Kotoulas, deployed via GitHub Pages. The entire site lives in `index.html` — all CSS, HTML, and JavaScript are inline with no build step, dependencies, or tooling.

## Architecture

`index.html` is structured in three sections:

1. **`<style>` block** — all CSS using CSS custom properties (`--bg`, `--fg`, `--accent`, etc.) defined on `:root`
2. **HTML body** — a fixed top nav (`#textNav`) and a scrollable content area (`#contentArea`) containing two tab pages: `#page-me` (bio) and `#page-research` (publications list)
3. **`<script>` block** — `switchTab(tab)` manages active state and triggers CSS fade/blur animations by toggling `.active` / `.visible` classes

## Workflow

After making any file changes, always stage, commit, and push to `main`.

## Deployment

Push to `main` → GitHub Pages auto-deploys. The `CNAME` file sets the custom domain.

## Content updates

- **Bio/contact**: edit `#page-me`
- **Research entries**: add/edit `.index-row` divs inside `#page-research`; each row has `.index-row-year`, a title div (optionally wrapped in `<a>`), `.index-row-desc` for authors, and `.index-row-cat` for status
- **Tabs**: `switchTab` is called via `onclick` on `.tab-link` elements; adding a new tab requires a new `.tab-link` in the nav and a corresponding `#page-<name>` div in `#contentArea`
