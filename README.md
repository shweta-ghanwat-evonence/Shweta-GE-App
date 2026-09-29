# Shweta-GE-App

Pilot repo for the Release Notes Writer automation. Every PR merged to `main`
is meant to trigger `.github/workflows/release-notes.yml`, which forwards the
merged PR's data to an Application Integration endpoint for classification
and release publishing.

Design and full build status live in the
[LowCodeAgent repo](https://github.com/) (`docs/automation.md`,
`feature_list.json`) — this repo is just the pilot target, not the source of
truth for the pipeline itself.

**Status as of 2026-09-29:** the workflow below is pushed but not yet live -
`RELEASE_NOTES_ENDPOINT` and `RELEASE_NOTES_TOKEN` aren't set yet (they
depend on `automation-003`, the Application Integration flow, which doesn't
exist yet). Until those secrets exist, a merge here will trigger the
workflow but the `curl` step will fail harmlessly (no endpoint to call).
