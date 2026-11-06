---
uid: jndt5wa3md5n0mayf8438
title: Code Rules for Documentation and Comments in Code
modified: Friday, November 6th 2026, 6:35 pm
created: Friday, November 6th 2026, 6:23 pm
---

# Code Rules for Documentation and Comments in Code
GAME DEV DOCUMENTATION AND COMMENT PRINCIPLES

CORE

- Explain why, not what.
  Code shows what it does. Comments show reasoning, decisions, and/or constraints.
- Code documents implementation; comments document intent.
  If intent changes, update the comment.
- Don't duplicate code in comments.
  If a comment just restates the code, delete it.

API DOCS

Use for public functions, classes, and modules.

- Document the contract: what it does, parameters (with units and ranges),
  return values, and side effects.
- Flag dangers: performance issues, crash risks, and important notes.
- Add a short usage example for non-trivial functions.

INLINE COMMENTS

Use inside function bodies.

- Comment the surprising, not the obvious.
  Good for: workarounds, ordering requirements, magic numbers,
  and warnings like "changing this breaks saves".
- Write for the future fixer and extender.
  Explain invariants, pitfalls, and non-obvious choices.
- Keep them short.
  Long explanations belong in API docs or design docs.

HYGIENE

- Fix code, not comments.
  Don't use comments to patch bad names or messy code. Rewrite it.
- Update outdated comments.
  An incorrect comment is worse than no comment.
- Be consistent.
  Example: capital letter, end with period, put comments above the code.

 SUMMARY

- Explain why, not what.
- Document the public contract.
- Comment the surprising, not the obvious.
- Fix code instead of commenting around it.
- Delete dead code and update stale comments.