# Sked legal site agent rules

This is the Sked marketing/legal GitHub Pages site.

## Proof-first PR rule

Mark reviews proof, not Swift or Kotlin diffs. Every PR must include:

1. A "Done when" line written as user-visible behavior.
2. Proof: simulator screenshots or video of the real flow, on iPhone 17e and in dark mode where relevant.
3. Tests for money, time and timezone, and deletion logic.
4. A second-model review of the diff (pstack /interrogate or Codex), linked or pasted.
5. A risk checklist in the description, each answered Yes or No:
   - Touches stored data or migrations?
   - Auth, tokens or secrets?
   - Permissions or Info.plist?
   - New third-party SDK or analytics?
   - Deletes anything?
   - Store-facing text or privacy labels?
   - Easy to roll back?

If any answer is Yes (or rollback is No), the agent writes a plain-English walkthrough of that part (a diagram is fine) and flags it to Mark before merging. If all are No, the PR merges on the proof. If the same mistake shows up twice, turn it into a lint rule or test.

### Release notes and build numbers
- TestFlight builds get What to Test notes covering changes since the previous build.
- App Store What's New comes from the real code diff since the last submitted build.
- Xcode Cloud and local builds share one build-number sequence. Next build number for Sked: 209.
