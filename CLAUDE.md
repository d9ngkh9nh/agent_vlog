# CLAUDE.md - frontend website rules

## Project Overview
This project is a frontend website prototype built for fast iteration and visual review.
Claude should prioritize clean implementation, strong visual polish, and minimal complexity.

## Working Style
- For non-trivial changes, first give a short plan before editing code.
- Keep changes focused on the user's request; do not add extra sections, features, or content.
- Prefer simple solutions over heavy abstractions.
- When requirements are ambiguous, ask the minimum clarifying question needed to proceed.

## Frontend Defaults
- Default output is a single `index.html` file unless the user asks for a different structure.
- Keep styles inline unless the user requests separate CSS or a framework setup.
- Use Tailwind CSS via CDN unless the user says otherwise.
- Build mobile-first and ensure the layout remains responsive.
- Use placeholder copy and `https://placehold.co/` images when real content is not provided.

## Brand Assets
- Always check the `brand_assets/` folder before designing.
- If brand assets exist, use them instead of placeholders.
- If a logo, palette, or style guide is present, follow those assets exactly.

## Design Rules
- If a reference image is provided, match the layout, spacing, typography, and colors as closely as possible.
- When matching a reference, do not improve, expand, or redesign it.
- If no reference is provided, design from scratch with a high-quality, modern look.
- Avoid generic-looking defaults.
- Do not use `transition-all`.
- Every interactive element should have hover, focus-visible, and active states.

## Visual Review
- Always preview the site on localhost before final review.
- Do not rely on raw code alone for visual accuracy.
- When screenshots are part of the workflow, compare the result against the reference and fix visible mismatches before stopping.
- Pay attention to spacing, typography, alignment, colors, border radius, shadows, and image treatment.

## Local Commands
- Start the local server with: `node serve.mjs`
- Default local URL: `http://localhost:3000`

## Guardrails
- Do not invent brand colors if a brand palette already exists.
- Do not add sections or features that were not requested.
- Do not stop after the first visual pass when the task requires matching a reference.
- Keep code readable and easy to edit in future iterations.

## When Updating This File
- Keep this file concise.
- Add only rules that are repeatedly useful across sessions.
- Move machine-specific setup and detailed design workflows into separate docs or scoped rule files.


## Screenshot Workflow
- **Always screenshot from localhost:** `node screenshot.mjs http://localhost:3000`
- Screenshots are saved automatically to `./temporary screenshots/screenshot-N.png` (auto-incremented, never overwritten).
- Optional label suffix: `node screenshot.mjs http://localhost:3000 label` → saves as `screenshot-N-label.png`
- `screenshot.mjs` lives in the project root. Use it as-is.
- After screenshotting, read the PNG from `temporary screenshots/` with the Read tool — Claude can see and analyze the image directly.
- When comparing, be specific: "heading is 32px but reference shows ~24px", "card gap is 16px but should be 24px"
- Check: spacing/padding, font size/weight/line-height, colors (exact hex), alignment, border-radius, shadows, image sizing