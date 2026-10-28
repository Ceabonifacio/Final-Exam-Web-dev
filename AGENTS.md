# CampusCycle - Codex Build Instructions

## 1. Goal

Build **CampusCycle**, a simple, polished, responsive website prototype for a student marketplace where students can browse, buy, sell, or exchange pre-owned school supplies.

Follow the visual direction in `Target Design.pdf` and use the existing `Logo.svg`. Implement only the course requirements described below.

**K.I.S.S.: Keep it simple.** Prioritize a clear layout, readable text, working page links, responsive CSS, and a consistent brand. Do not overengineer.

## 2. Required technology and hard limits

- Use **HTML5 and CSS3 only** for the website.
- Do not add JavaScript, inline event handlers, frameworks, libraries, a backend, a database, build tools, package managers, or server-side code.
- The pages must open locally in a browser without a backend server.
- Use one external stylesheet: `css/styles.css`.
- Use semantic HTML5: `header`, `nav`, `main`, `section`, and `footer` where appropriate.
- Use meaningful class names, consistent indentation, descriptive image `alt` text, and valid metadata (`charset`, `viewport`, and page title).
- Do not use fake functionality. Any search box, category chip, form, or button that is only a visual example must not claim it actually searches, submits, stores, or processes data.
- Do not add login, cart, checkout, payments, messaging, account dashboards, or other out-of-scope features.

## 3. Before creating or changing files

Complete this preflight first. Do not start implementation until these checks are complete.

1. Inspect the existing project and read any existing `README.md` and `AGENTS.md` instructions before changing files.
2. Locate `Target Design.pdf` and inspect its pages/visuals. It is the main visual reference, not a requirement to copy every pixel exactly.
3. Locate the user's existing `Logo.svg`. Preserve its artwork; do not invent or replace the logo. Use its actual relative path. If it cannot be found, use a clearly marked temporary placeholder and report that the logo file is missing.
4. Review all requirements in this file and produce a short implementation plan.
5. Check the repository for existing assets before downloading, duplicating, moving, or recreating any files.
6. If something essential is missing, use the simplest safe fallback and report the limitation. Do not silently invent real contact details, partnerships, customer reviews, or statistics.

## 4. Parallel subagent workflow

If the current Codex runtime supports subagents, delegate the following **four independent, read-only checks concurrently** before implementation. Wait for all results and combine them into one concise plan. Use no more than four simultaneous subagents and do not create nested subagents unless a real blocker requires it.

- **Designer Agent:** Inspect `Target Design.pdf` and report the key layout, page structure, colors, imagery, and visual patterns to preserve.
- **HTML and Accessibility Agent:** Turn the required page content into a semantic HTML checklist. Check readability, navigation clarity, image alt text, and keyboard focus requirements.
- **Responsive CSS Agent:** Recommend simple desktop/tablet/mobile layout rules and likely overflow risks. Do not write or edit project files.
- **Asset and Brand Agent:** Locate `Logo.svg` and existing assets; recommend a minimal set of icons and product visuals consistent with the reference. Do not replace the logo or edit source files.

After implementation, use read-only subagents in parallel when supported:

- **Reviewer Agent:** Check every requirement in this file against the completed pages and report specific defects with file names/sections.
- **Responsive Reviewer Agent:** Review desktop, tablet, and mobile layouts, especially navigation, product cards, text wrapping, and horizontal overflow.
- **Accessibility Reviewer Agent:** Check contrast, readable type, focus states, semantic structure, and useful image alternatives.
- **Debugging Agent:** Investigate reported defects and recommend the smallest fixes. The main Codex agent remains the only writer of shared source files, to prevent concurrent edit conflicts.

If subagents are not available, do the same checks sequentially as explicit review passes. Do not claim that subagents ran if they did not. Agent names describe responsibilities, not separate software components that must be added to the website.

## 5. Brand and visual direction

Use `Target Design.pdf` as the guide for a friendly, minimal, student-focused marketplace. The reference features a soft cream canvas, dark green text/footer, a prominent home-page hero, pastel product cards, a three-step “Browse / Connect / Reuse” section, and a dark footer.

Use these exact brand colors:

- Cream: `#FDFFD8` - main page background.
- Lavender: `#E3D9EE` - alternate section/card background.
- Light cyan: `#D3F9FF` - alternate product card/accent.
- Soft coral: `#FFAE9F` - small highlights and decorative details.
- Fresh green: `#85C78F` - primary accent and CTA background.

Use a dark green/charcoal support color for body text and the footer so text remains readable against the pastel colors. Keep the pastel palette soft; do not apply all colors equally to every section. Use dark text on the fresh-green buttons rather than low-contrast white text.

### Typography

- Use **Poppins** for headings and prominent titles.
- Use **Inter** for body copy, product details, navigation, prices, and buttons.
- Use sensible sans-serif fallbacks.
- Keep body text at a comfortable size (normally at least `16px`), use clear line-height, and avoid tiny labels.

Google Fonts can be linked through HTML `<link>` elements; this does not require JavaScript. If the fonts do not load, the system sans-serif fallback must keep the site readable.

### Logo and icons

- Use the existing `Logo.svg` exactly as provided, maintaining its proportions. Do not redraw, recolor, crop, or distort it.
- Prefer **Google Material Symbols** for small interface icons because Google provides them for web use. Use only a few relevant symbols, such as `menu_book`, `group`, `autorenew`, `sell`, `eco`, and `arrow_forward`.
- Load icons through the official Google Fonts Material Symbols stylesheet or use local SVG icon assets from Google's Material Symbols library when practical. Do not use JavaScript to load icons. Provide text labels where needed; icons must not be the only way to understand a control.
- The LeetCode problemset is not an icon library. Do not copy its logo or branded interface elements.
- For product visuals, prefer existing local assets. If none exist, use a small set of tasteful, locally stored SVG illustrations or properly reusable images. Do not depend on remote image URLs for product cards. Record the source of any downloaded third-party asset in `README.md`.

## 6. Required files and simple structure

Create or update only what is needed. Prefer this structure:

```text
project-root/
├── AGENTS.md
├── README.md
├── index.html
├── services.html
├── about.html
├── css/
│   └── styles.css
└── assets/
    ├── images/
    │   └── products/
    └── icons/
```

Use the existing location of `Logo.svg` if moving it is unnecessary. If moving it into `assets/images/` is clearly safe in an otherwise new project, preserve the original file contents and update every reference. Do not create unnecessary CSS files or folders.

The pages must link to each other using relative paths and share the same navigation, branding, and footer:

- `index.html` - Home
- `services.html` - Marketplace
- `about.html` - About Us
- `css/styles.css` - shared styling

## 7. Page requirements

### Page 1 - Home (`index.html`)

Match the home-page direction shown in `Target Design.pdf`:

- Header with the logo, links to Home / Marketplace / About Us, and a clear CTA link to the Marketplace.
- Hero with this headline: **“Find affordable school supplies. Give pre-loved items a new purpose.”**
- One short supporting paragraph explaining that students can discover pre-owned school supplies within their school community.
- Primary CTA: **“Explore Marketplace”**, linking to `services.html`.
- Secondary link: **“How it works”**, linking to the relevant section of `about.html`.
- A visually balanced hero image/collage of school supplies on desktop; stack the content cleanly on mobile.
- Featured items or benefits, followed by a simple “Browse / Connect / Reuse” explanation.
- Shared footer with page links and placeholder contact information.

### Page 2 - Marketplace (`services.html`)

Use the marketplace look from the reference: cream background, a clear page heading, and tidy product cards with generous spacing.

- Page heading: **“Pre-loved. Ready for you.”** or **“Find Your Next School Essential.”** Choose one that best matches the reference and keep it consistent.
- Brief introduction and simple visual category labels: Textbooks, Uniforms, Calculators, and Other Supplies.
- Show these six sample product listings in a clean grid. Use three columns on wide screens, two on medium screens, and one on narrow mobile screens.

| Product | Price | Condition |
| --- | ---: | --- |
| Used Mathematics Textbook | ₱250 | Good Condition |
| Scientific Calculator | ₱450 | Like New |
| College Uniform Top | ₱300 | Good Condition |
| Programming Textbook | ₱350 | Good Condition |
| Student Backpack | ₱400 | Very Good Condition |
| Art Supplies Set | ₱150 | Good Condition |

- Each card must show an image/illustration, product name, condition, price, and an **“Inquire”** link to the About page contact section (`about.html#contact`).
- Mark the listings as sample prototype content, using a short note such as: “Sample listings for the student website prototype.”
- Categories and inquiry links must not imply real filtering, inventory, or transaction processing.
- Include the shared header and footer.

### Page 3 - About Us (`about.html`)

Follow the simple pastel About Us direction in the reference and include the required startup/team/contact information:

- Header and shared navigation.
- Page title and short introduction to CampusCycle.
- A mission statement: make school supplies easier to access and encourage students to reuse useful items.
- A three-step section with the heading **“New to CampusCycle? It’s simple.”** and steps:
  1. **Browse** - Explore pre-loved textbooks, uniforms, calculators, and other supplies.
  2. **Connect** - Inquire about an item and discuss details with its owner.
  3. **Reuse** - Give useful supplies a new home and keep the cycle going.
- A benefit section using this headline: **“Good for your pocket. Great for your community.”** Include concise points for Affordable Supplies, Convenient Discovery, and Less Waste.
- Team member: **Cyril Enzo Albert S. Bonifacio**.
- A contact section with a visible placeholder such as **“Facebook link to be added”** and a clearly marked placeholder email. Do not invent a real Facebook URL or personal email.
- A contact form is optional. Prefer not to add one unless it improves the reference design; if included, label it as a visual-only form and do not imply it submits anywhere.
- Include the shared footer.

## 8. CSS and responsive requirements

Use one external stylesheet and simple, reusable classes. Use CSS Grid and/or Flexbox for layout, the CSS box model correctly, and media queries for smaller screens.

- Desktop reference width: around `1440px`.
- Tablet check: around `768px`.
- Mobile check: around `390px`.
- Use a centered content container and consistent horizontal spacing.
- Use a three-column product grid on wide screens, two columns on medium screens, and one column on narrow screens.
- Let mobile navigation wrap or stack neatly. Do not add a JavaScript hamburger menu.
- Ensure images use `max-width: 100%` and do not stretch out of proportion.
- Avoid fixed widths that force horizontal scrolling. Use fluid widths, `minmax()`, and appropriate breakpoints.
- Add clear `:hover` and `:focus-visible` styles to links and interactive controls. Ensure keyboard focus is visible.
- Aim for strong contrast: at least 4.5:1 for normal text where possible. Do not place small text on similarly colored pastel backgrounds without a dark text color.
- Buttons/links must have readable labels and comfortable tap areas. The visible CTA must be a real link to a page or section.
- Include `alt` text for meaningful images. Use `alt=""` only for decorative images.

## 9. K.I.S.S. rules

- Do not add features beyond the three pages described above.
- Do not build a custom design system, complex animations, carousels, modal dialogs, filters, or mobile-menu logic.
- Avoid excessive gradients, shadows, rounded containers, decorative effects, and competing accent colors. Use them sparingly.
- Reuse the same header, footer, card, button, spacing, and color styles across pages.
- Prefer clear content and generous spacing over decoration.
- Do not add placeholders that look like working functions when they are not functional.
- Keep `README.md` short and include the project purpose, file structure, local opening instructions, HTML/CSS-only limitation, and asset credits.

## 10. Build, review, and debugging loop

Use this loop; do not simply write files and stop.

### Pass 1 - Preflight (before code)

- Confirm the design reference and logo location.
- Check the three-page scope, style tokens, navigation, assets, and responsive requirements.
- Complete the parallel subagent review in Section 4 if supported.
- Make a brief checklist of risks and then begin implementation.

### Pass 2 - Build

- Implement the three HTML pages, shared stylesheet, needed local assets, and `README.md`.
- Keep the HTML/CSS consistent with the approved plan.
- Do not create JavaScript files or add JavaScript to HTML.

### Pass 3 - Independent review

- Ask the Reviewer, Responsive Reviewer, and Accessibility Reviewer to inspect the completed project in parallel if subagents are supported.
- Check internal page links, CSS references, image paths, missing assets, semantic structure, responsive rules, hover/focus states, and text readability.
- Review at desktop, tablet, and mobile widths using available browser/preview tools. If visual browser testing is unavailable, inspect the HTML/CSS carefully and explicitly report that limitation.

### Pass 4 - Fix and repeat

- Fix all confirmed critical or high-impact problems first; then fix smaller visible issues.
- Have the Debugging Agent investigate issues if supported; it should report the smallest safe fix, while the main agent coordinates edits.
- Re-run the same checks after each fix. Repeat the review/fix cycle for up to three passes or until no critical/high-impact issues remain.
- Do not rewrite working parts just for stylistic preference. Do not claim the project is perfect; report what was actually checked and any remaining limitations.

## 11. Definition of done

The project is ready when all of the following are true:

- [ ] `index.html`, `services.html`, and `about.html` exist and are connected by working relative links.
- [ ] Every page uses `css/styles.css` and has title, charset, and viewport metadata.
- [ ] Semantic HTML elements and meaningful alt text are used appropriately.
- [ ] The existing logo is used without redesigning it.
- [ ] The specified five brand colors, Poppins headings, and Inter body text are applied consistently, with readable contrast.
- [ ] The home page, six sample product cards, About Us content, team name, and contact placeholder are present.
- [ ] Google Material Symbols or local equivalent SVG icons are used sparingly and do not require JavaScript.
- [ ] Responsive layouts work or have been reviewed at approximately 1440px, 768px, and 390px widths without avoidable horizontal overflow.
- [ ] Links, hover states, and keyboard focus states are visible and understandable.
- [ ] No JavaScript, framework, backend, database, or build step has been introduced.
- [ ] `README.md` explains how to open the site locally and records third-party asset sources.
- [ ] The final response briefly lists created files, checks performed, and any remaining limitations.

## 12. References

These references inform the workflow and icon choice; the visual and functional requirements come from the project owner's brief and `Target Design.pdf`.

1. OpenAI, “Iterating Development Workflows with Codex,” Aug. 2026. [Online]. Available: https://developers.openai.com/cookbook/examples/codex/iterating-development-workflows-with-codex
2. OpenAI, “Subagents.” [Online]. Available: https://learn.chatgpt.com/docs/agent-configuration/subagents
3. Google for Developers, “Material Symbols guide.” [Online]. Available: https://developers.google.com/fonts/docs/material_symbols
4. OpenAI, “Codex Prompting Guide.” [Online]. Available: https://developers.openai.com/cookbook/examples/gpt-5/codex_prompting_guide
