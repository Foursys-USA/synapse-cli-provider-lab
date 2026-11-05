# Synapse CLI Provider Lab

Isolated playground for CLI provider order, model/source fallback and auth/quota failures.
Never point a production demand here. Never point a lab demand at a production project.

## Live objects

- Seat project: CLI Provider Lab - 05711eab-995a-4bd3-8b20-6119b0fe3df2
- James project: c7c2480d-3806-411e-a5e9-41b5a44572e3
- James company: 12458f8f-d04e-4851-af3f-71e1c37cfb9f
- Source: Foursys-USA/synapse-cli-provider-lab, branch main
- CLI provider order: james
- Small demands:
  - D-92D2D7 - 92d2d7c6a42d3d6b - add farewell(name)
  - D-388D9F - 388d9f09a94a7fa1 - add initials(name)
  - D-4DA1F0 - 4da1f00361853593 - document the pytest command

## Drills

1. Prism model to Prism model
   Keep James CLI primary. Disable the first Prism model in JamesCLI. The next Prism model must run.
   Restore it after the run.

2. Prism to Foundry inside James CLI
   Disable the Prism source in JamesCLI. The James CLI must run on gpt-5-chat from Foundry.
   Verify the terminal/usage says Foundry. Restore Prism immediately.

3. Foundry to next CLI (Codex)
   Requires Codex connected in Settings -> CLI Providers and secondary codex in this project.
   Disable Prism and Foundry. The James CLI has no source left, so the runtime must try Codex.
   Restore both sources and the project order after the run.

4. Cursor / Claude / Agy
   Add them to the same global catalog only after their adapter/auth is enabled, then repeat the order drills.

## Rules

- Restore every global source/provider toggle immediately, even when a drill fails.
- One drill at a time.
- Use only the small demands above; do not create broad demands here.
- All tokens and keys stay server-side; never commit credentials.
