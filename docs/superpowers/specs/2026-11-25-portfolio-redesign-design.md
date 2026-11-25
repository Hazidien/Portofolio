# Portfolio redesign design

## Intent

Move the existing Hazidien portfolio into the empty `Hazidien/Portofolio` repository and make it easy for a first-time visitor to understand who Hazidien is, what work he has done, and how to contact him. Preserve factual project and career information while explaining it in plain English.

## Goals

- Put the introduction, selected work, experience, education, skills and contact details in a clear order on one page.
- Make project titles and summaries understandable to people who do not work in GIS. Keep useful methods and results, and explain specialist terms briefly where needed.
- Make CV and portfolio downloads easy to find.
- Improve keyboard use, screen-reader structure, contrast, responsive layout and reduced-motion behavior.
- Reuse the source repository's relevant portrait, project imagery, CV and portfolio files, and repair broken media links.

## Non-goals

- Add a framework, build pipeline, animation system, project filtering or project-detail modal.
- Rewrite or invent qualifications, job history, project outcomes or contact details.
- Change the old repository.

## Approaches

1. **Single-page portfolio (chosen).** One page with a compact navigation, strong introduction, featured project summaries, professional background and contact links. This matches the request for a simpler experience and reduces the number of choices a visitor must make.
2. **Small multi-page site.** A landing page plus separate project and CV pages. It would provide more room for each project but requires more navigation and page structure than needed for the current content.
3. **Retain the long page and refine it.** Keep the current eight-item navigation, project filters and modal details while improving styling. This makes fewer structural changes but retains the discovery steps that make the current page harder to follow.

## Content and interaction

- Keep a small navigation for Work, About and Contact, plus a visible CV link.
- Open with Hazidien's name, role, one plain-language sentence describing his work, and clear actions to view projects, download the CV and contact him.
- Lead with three representative projects: rooftop solar analysis in Surabaya, forest-change monitoring in West Sumatra, and campus transit-stop planning. Include the remaining existing projects in the same work section with concise explanations, so the redesign does not erase portfolio material.
- Each project summary should make the problem, Hazidien's contribution and a supported result clear. Keep technical methods secondary and define necessary terms in ordinary language. Make live demos clear about their availability; retain their original destinations.
- Present experience and education as short, scannable entries; present skills as a compact set of plain-language groups rather than a logo wall.
- Keep the contact links and existing CV/portfolio downloads direct. Remove category filters and pop-up details; project content should be readable on the page.

## Visual direction

- **Mode:** Experience. The project work and its maps should lead; interface elements should stay quiet and obvious.
- **Palette:** paper white `#F7F9F6`, deep forest `#19372D`, map green `#286B50`, river blue `#397E91`, warm survey yellow `#D5A32E`, and readable secondary text `#53615A`.
- **Type:** DM Sans for headings and body text, with comfortable body sizing and short line lengths. Use sentence case and a clear size hierarchy.
- **Layout:** left-aligned, single-column reading flow with a bounded content width. On wide screens, use a two-column introduction with portrait; project imagery sits beside concise text. Stack all content on narrow screens.
- **Distinctive element:** use the existing geospatial project images as the visual proof of work, with a restrained map-green and river-blue palette. Avoid decorative map grids that compete with real project imagery.

```text
Name                         Work  About  Contact  [Download CV]

Hazidien Ramadhan Utomo       [Portrait]
GIS analyst turning location data into useful plans.
[See my work] [Download CV] [Contact]

Selected work
[Project image]  Rooftop solar in Surabaya — what was studied / result
[Project image]  Forest change in West Sumatra — what was studied / result
[Project image]  Better campus transit stops — what was studied / result
Other projects as short, readable entries

About and experience | Education | Skills
Contact details
```

## Accessibility and quality

- Use semantic landmarks, one clear page-level heading, ordered headings, a skip link and descriptive link names.
- Ensure all controls work by keyboard, show a visible focus state, and expose the mobile navigation's expanded state to assistive technology.
- Use useful alternative text for informative images and empty alt text for decorative images. Preserve legibility at zoom and on small screens.
- Verify text and control contrast, honor reduced-motion preferences, and do not require hover or color alone to understand content.
- Preserve all existing outbound destinations and only claim results supported by the source content.

## Constraints and builder calls

- Source: `Hazidien/hazidien-portfolio` on `main`; destination: currently near-empty `Hazidien/Portofolio` on `main`.
- The source is static HTML/CSS/JavaScript. Keep that stack and avoid new dependencies.
- The source contains many media files and some large assets. Copy only files needed by the redesigned page and its existing CV/portfolio links; do not carry over unused background or poster files.
- The builder chooses the exact card/row treatment, breakpoints and implementation details, and checks all copied asset paths and outbound links.
- No production-code changes begin until this design is approved.
