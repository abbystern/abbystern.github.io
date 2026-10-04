# Portfolio site plan

Status: Awaiting approval. No website implementation or starter cleanup yet.

## Site and content

- Build a static Jekyll user site at `https://abbystern.github.io`, with `baseurl: ""` and Jekyll URL filters for internal links and assets.
- Home: a short first-person introduction with Abby Stern’s name and a line about her interest in technology, data, strategy, and operations. End with “Let’s connect” links to LinkedIn and email.
- Use the supplied portrait on the Home page, optimized for fast loading with explicit dimensions and descriptive alt text. Store the website copy in root-level `assets/`.
- About: use the supplied first-person text, removing stray `Abby_Stern_Resume` labels and the contact instructions accidentally included with the copy.
- Work Experience: use the uploaded résumé for exact titles, dates, and achievements at NetApp (Summer 2026), NextBound (Spring 2026), KIPP NYC (2021–2025), and City Year (2020–2021), plus earlier experience at Cone Health and NC State University. Preserve qualifications such as “estimated” and “projecting” when presenting metrics. Clearly mark any remaining missing details as placeholders.
- Contact: show `abbyestern@gmail.com` as a public mailto link and `https://www.linkedin.com/in/abbystern98/`. Do not use a Berkeley email address. Email links require a configured email app.
- Include simple top navigation and a shared footer across all four pages. Do not invent achievements, metrics, employers, clients, or projects.

## Design

- Light theme only; responsive, single-column layouts with generous whitespace.
- White or off-white backgrounds, dark text, deep teal links/buttons/heading details, occasional sage-tinted sections, and sparse mustard highlights.
- Never use sage or mustard for text on light backgrounds. Verify accessible contrast for text and interaction states.
- Clean modern sans-serif body typography and warmer, distinctive headings; friendly, professional, conversational tone.
- Use the user’s descriptions of reference websites only; do not fetch them.
- Semantic HTML, keyboard-accessible navigation, visible focus states, and a skip link. No animation system or unnecessary libraries.

## Structure and technical choices

- Place `index.md`, `about.md`, `work-experience.md`, `contact.md`, `_config.yml`, `_layouts/`, `_includes/`, and `assets/` directly in the repository root.
- Markdown and YAML front matter hold content; reusable HTML layouts/includes and plain CSS hold design. Minimal JavaScript only if necessary.
- Use GitHub Pages-supported Jekyll SEO and sitemap plugins, plus a favicon. No backend, database, blog, CMS, contact form backend, trackers, React/Vite app, Node application, or monorepo.
- After approval, remove the unused starter app packages, application folders, package manifests/lockfiles, and associated app workflows/registrations. Preserve the supplied brief and essential platform metadata where needed; exclude non-site support files from Jekyll output.
- Include a README with editing instructions, local Jekyll preview steps, Lighthouse instructions, and GitHub Pages setup for the `main` branch and `/ (root)`. GitHub Pages performs the build; no manual build step is needed to publish.

## Verification

- Build with the GitHub Pages-compatible Jekyll toolchain and check all navigation, contact links, SEO output, sitemap, and assets.
- Check the site at 375px and 1280px widths.
- Run Lighthouse and target at least 90 in Performance, Accessibility, Best Practices, and SEO; report actual scores and any verification limits honestly.
- Confirm the complete website is at the repository root and can publish from `main` and `/ (root)` with no separate application remaining.

## Assumptions and missing information

- The uploaded résumé supplies education, work history, achievements, skills, and interests. Use it alongside the supplied About text; do not fetch personal information from external sources.
- Do not publish the résumé’s phone number or Berkeley email, or offer the original PDF as a public download. Use only the approved Gmail address and LinkedIn link for contact.
- Both LinkedIn and email will be displayed.
- The initial homepage line may be adapted from the supplied About text without adding new factual claims.
- GitHub account/repository access has not been provided. The deliverable is a publish-ready repository; enabling GitHub Pages or pushing to GitHub is not part of this build unless separately requested.