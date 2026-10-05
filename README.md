# titan-android

The TITAN Android app. First a minimal app that is part of the working version: sign-in, a notification stream over the app's own connection to the node, and notifications with Snooze, Done, Approve and Reject (decisions #14, #23). Later the full app: chat, today, domains.

Part of TITAN, a self-hosted personal AI assistant, planner and tracker. The
product, architecture and rules shared by every TITAN repository are in the
`shared/` submodule ([titan-shared](shared/README.md)).

## Contents

- **Minimal app** (working version): sign-in, the notification stream in a foreground service, notifications with their actions.
- **Full app** (later): chat with approvals, today, tasks, reminders, calendar, trackers, notes.
- **API client** generated from `shared/contracts/`.

## Status

Not started. The minimal app is build-plan stage 7; the full app comes after the working version. See the [build plan](shared/docs/roadmap/plan.md).

## Getting the code

```sh
git clone --recurse-submodules https://github.com/titan-home/titan-android.git
# after a pull:
git submodule update --init
```

## Licence

Released into the public domain under [the Unlicense](LICENSE).
