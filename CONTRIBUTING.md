# Contributing to Driftwood

Thanks for taking the time. This repo is the **hub**: the README, the documentation, and the downloads players install. The code lives elsewhere.

## Where things actually live

| You want to | Go to |
|---|---|
| Report a bug in the Driftwood app, or ask for a feature | [an issue on this repo](https://github.com/HumanGenome/Driftwood/issues) |
| Report a bug in the dedicated server package | [HumanGenome/DriftwoodServer](https://github.com/HumanGenome/DriftwoodServer/issues) |
| Report a security vulnerability | [private reporting](.github/SECURITY.md), never a public issue |
| Fix a typo or a wrong instruction in this README | a PR here |

The Driftwood app's source is not public, so app bugs are fixed by us rather than by PR. A good bug report is worth more than a patch here: say what you did, what happened, what you expected, your Driftwood version (it is in the app's footer), and whether the server is one you run or one you rent.

## What makes a report actionable

- **The exact text of any error**, not a description of it.
- **Whether it reproduces**, and what changes when it does not.
- **Which side you think it is.** "Connect does nothing" and "Connect works but the world is empty" are different faults in different repos, and saying which you saw saves a round trip.
- **Log files** if you have them. The app writes its own; the server writes to its host's log directory. Redact anything you would not post publicly, server addresses included.

## What this project will not do

- Ship any part of How to Fish. You bring your own Steam copy, on both sides.
- Work around the game's own bugs by pretending they did not happen. If the server cannot host correctly it refuses and says why.
- Claim a feature in this README that the software does not do.

## Reporting a security issue

See [.github/SECURITY.md](.github/SECURITY.md). Please do not open a public issue for a vulnerability.
