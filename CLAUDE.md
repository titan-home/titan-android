# CLAUDE.md: titan-android

The TITAN Android app. First a minimal app that is part of the working version: sign-in, a notification stream over the app's own connection to the node, and notifications with Snooze, Done, Approve and Reject (decisions #14, #23). Later the full app: chat, today, domains.

Read and follow, in this order:

1. [Rules for AI agents](shared/docs/development/ai-agents.md) — what you may
   and may not do. They override your defaults.
2. [Development rules](shared/docs/development/rules.md) — how we work, for
   every repository.
3. [Documentation index](shared/docs/README.md) — product, architecture,
   decisions, build plan.

`shared/` is the `titan-shared` submodule. Never edit files under it from this
repository; change `titan-shared` through its own pull request.

## Stack and commands

- Kotlin with Jetpack Compose; ktlint; unit tests and Robolectric.
- Design tokens come from `shared/design/`.

Commands are added here as the code arrives.

## Rules specific to this repository

- The device token is stored only in Android's encrypted storage; never log it.
- The notification stream runs in a foreground service; the app asks once for an exemption from battery optimisation and explains why.
- Losing the connection never clears data on screen; writes are never queued.
- Every user-visible string is a translated resource; English, Russian and Ukrainian first.

## Before committing

Run this checklist before every commit
([development rules, "Before committing"](shared/docs/development/rules.md#before-committing)).
The commands are settled as the code arrives.

1. ktlint passes.
2. Unit tests pass for the modules the commit touches. The full suite runs in
   CI.
3. If Gradle files or dependencies changed: the debug build succeeds.
4. If user-visible text changed: every language has the same string
   resources.
5. If Markdown or the `shared/` pointer changed:
   `python3 shared/scripts/check_links.py .` prints nothing.
