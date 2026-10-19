# seedance-clip

A Claude Code skill for Dreamina Seedance 2.5 video generation on the BytePlus ModelArk API. It writes Seedance prompts, builds the request, and never submits a paid request without your approval.

## What it covers

- Approval gates: show every request before send, draft at 480p first, no auto-retry
- API setup, task types (text-to-video, first frame, reference, edit, extend) and request limits
- Draft-then-final flow
- Prompt method: asset binding, shot plans with timestamps, camera words, sound, constraints
- Ad templates (UGC, product commercial, kinetic type, image-to-video, flash sale)
- A ladder for on-screen text, which Seedance often misspells

## Install

```bash
git clone https://github.com/tomaibuilder/seedance-clip-skill ~/.claude/skills/seedance-clip
```

Put your BytePlus key in an `.env` file as `ARK_API_KEY`. Then ask Claude Code to "make a Seedance clip".

## Notes

- Written for my own workspace. Some paths (`VOICE.md`, `Content Creation/...`) point to my vault. Change them to your own folders.
- Section 5b and the `references/` files come from research, not yet fully tested. Check the BytePlus docs if a rule looks stale.
