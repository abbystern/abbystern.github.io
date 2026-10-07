---
name: Root Jekyll preview
description: Why this portfolio uses a non-artifact preview workflow rather than an app scaffold.
---

A root-only Jekyll deliverable should be previewed through a custom workflow serving the actual Jekyll source, not through a separate app scaffold.

**Why:** The artifact factory’s app scaffolds introduce nested packages and application files that conflict with this user's explicit root-only publishing requirement.

**How to apply:** Use the workflow preview for this site. The platform can expose its preview as a legacy canvas iframe even when listArtifacts returns no registered artifacts. Do not create a React artifact just to register a preview.

The screenshot tool can capture the root workflow with `appPreview`, the Jekyll serving port, and a page path. Do not pass an artifact-directory identifier for this non-artifact site.

**Why:** Explicit artifact-directory resolution fails because this root workflow has no artifact registration; direct port-based captures work.

**How to apply:** Use direct port-based screenshots of the actual Jekyll site. Headless Chromium against the shared preview proxy is a fallback, not a reason to create a second app.