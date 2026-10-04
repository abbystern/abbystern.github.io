---
name: Root Jekyll preview
description: Why this portfolio uses a non-artifact preview workflow rather than an app scaffold.
---

A root-only Jekyll deliverable should be previewed through a custom workflow serving the actual Jekyll source, not through a separate app scaffold.

**Why:** The artifact factory’s app scaffolds introduce nested packages and application files that conflict with this user's explicit root-only publishing requirement.

**How to apply:** Use the workflow preview for this site. The platform can expose its preview as a legacy canvas iframe even when listArtifacts returns no registered artifacts. Do not create a React artifact just to register a preview.

The screenshot tool cannot resolve this root workflow as a normal artifact. Headless Chromium against the shared preview proxy can capture the actual site for visual checks.

**Why:** A non-artifact root workflow has no artifact directory registration for the screenshot resolver.

**How to apply:** Keep visual verification on the same generated Jekyll site; do not create a second preview app to work around the resolver.