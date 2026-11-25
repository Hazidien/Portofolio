# Portfolio redesign Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Replace the empty destination repository with a clear, accessible, one-page portfolio that preserves Hazidien's twelve projects and career details.

**Architecture:** Keep the existing plain HTML/CSS/JavaScript stack, but make the page content static and semantic so projects do not depend on JavaScript rendering or modal interactions. Use a small responsive stylesheet, browser-native links and disclosure for mobile navigation, and a carefully selected set of media copied from the source repository.

**Tech Stack:** HTML, CSS, small vanilla JavaScript only if needed for an accessible mobile menu, GitHub Pages static hosting, Pillow for local image optimization only (not a site dependency).

**Spec:** `docs/superpowers/specs/2026-11-25-portfolio-redesign-design.md`

## Global Constraints

- Keep one page and the existing static site stack; add no framework or site dependency.
- Preserve factual project and career information and explain specialist terms in ordinary English.
- Make CV and portfolio downloads direct and easy to find.
- Copy only media required by the redesigned page and its CV/portfolio links.
- The main content must work without JavaScript; keep project descriptions visible in the document.
- Do not change the original repository.

## Review Focus

- Missing copied media or document: check every local `src` and `href` resolves to an existing destination file.
- Mobile navigation: verify it can be opened and closed by keyboard, clearly announces its state, and fits a narrow viewport.
- External demos: confirm each retained link points to the original target and describe the Codespaces demos as temporarily available.
- Keyboard and zoom: check skip navigation, visible focus, sensible heading order, and layout at narrow width and browser zoom.
- Motion and contrast: check text/control contrast and ensure reduced-motion preferences suppress any nonessential movement.

---

### Task 1: Build the semantic portfolio content

**Files:**
- Create/modify: `index.html`
- Create: `assets/profile.jpg`
- Create: `assets/cv.pdf`
- Create: `assets/portfolio.pdf`
- Create: `assets/projects/solar-surabaya.webp`
- Create: `assets/projects/deforestation-west-sumatra.webp`
- Create: `assets/projects/campus-transit.webp`
- Do not copy source `script.js`; the destination clone contains only `README.md`

**Interfaces:**
- Consumes source facts from `work/hazidien-portfolio/index.html`, `script.js`, and the linked PDFs/images.
- Produces semantic page sections and stable local asset names consumed by the stylesheet in Task 2.

- [x] Copy the profile photo, CV PDF, portfolio PDF and three representative project images from their exact source paths; resize the project images to at most 1200 pixels wide and encode as WebP at quality 82 using installed Pillow.
- [x] Replace `index.html` with a semantic page containing a skip link, compact navigation, introduction, all twelve project summaries, experience, education, plain-language skill groups, direct downloads, and contact links.
- [x] Lead with rooftop solar, forest-change monitoring and campus transit; keep the other nine existing projects in a concise list in the same work section. For each entry, keep the problem, contribution or method, supported result, and original demo link when present.
- [x] Keep the page content in HTML and use a native `<details>` disclosure for the narrow-screen navigation so it works without JavaScript; do not copy the source filters, generated project cards, modal markup or inline event handlers.
- [x] Give informative images concise alt text, mark decorative content appropriately, make external destinations descriptive, and disclose that the Codespaces demos require an active session.
- [x] Check every local image/document reference against the files copied from the source; confirm the page has one H1 and ordered headings.

### Task 2: Apply the visual system and responsive accessibility

**Files:**
- Create/modify: `style.css`

**Interfaces:**
- Consumes section and navigation semantics from Task 1.
- Produces responsive layouts and visual states for links, buttons, the native navigation disclosure and project summaries.

- [x] Replace `style.css` with the approved paper-white, forest-green, river-blue and survey-yellow palette, DM Sans type, readable line lengths and clear spacing.
- [x] Build a wide-screen two-column introduction and featured project rows, then stack them at narrow widths without horizontal scrolling.
- [x] Add a visible skip link and strong `:focus-visible` styles; maintain clear contrast and minimum comfortable touch targets.
- [x] Respect `prefers-reduced-motion`; do not rely on hover, color, animation or imagery alone to explain content or expose actions.
- [x] Review the layout at a phone-sized viewport and at browser zoom; correct overflow, clipped navigation, text wrapping and focus visibility.

### Task 3: Document the new repository and review the finished site

**Files:**
- Modify: `README.md`
- Review: `index.html`, `style.css`, copied `assets/`

**Interfaces:**
- Consumes the final page and its asset paths from Tasks 1–2.
- Produces repository setup and GitHub Pages instructions matching the actual static files.

- [x] Replace the placeholder README with a short project description, local preview instructions, GitHub Pages setup, and the media path list.
- [x] Manually open the page at desktop and mobile sizes; verify the local CV and portfolio files respond and confirm email, LinkedIn, GitHub and project links are present.
- [ ] Open external destinations and confirm availability (not performed).
- [x] Inspect the final diff and confirm only selected assets, site files and documentation are included; confirm no source-repo files were modified.
- [x] Report manual review findings and any checks not performed; no automated tests are added for this static content change.
