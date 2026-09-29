# Shweta-GE-App

Pilot repo for the Release Notes Writer automation. Every PR merged to `main`
is meant to trigger `.github/workflows/release-notes.yml`, which forwards the
merged PR's data to an Application Integration endpoint for classification
and release publishing.

Design and full build status live in the
[LowCodeAgent repo](https://github.com/) (`docs/automation.md`,
`feature_list.json`) — this repo is just the pilot target, not the source of
truth for the pipeline itself.

**Status as of 2026-09-30:** live. The workflow authenticates via Workload
Identity Federation (no stored secret) and calls the
`release-notes-orchestrator` Application Integration flow directly. A merge
to `main` here creates and publishes a real, versioned GitHub Release
automatically.

## Automation status

This line was added by a real end-to-end test of the release notes automation.

## Test 2

Second real end-to-end test, after fixing the WIF auth step's missing
`token_format: access_token` (test 1, PR #1, failed with a 401 because
of that bug).
