# Puhguh submission

The submission files are `model.py` and `puhguh.pkl` in this repository root.
Use both files from the same revision. The model source contains all runtime
classes and precomputed data; no additional team modules or data files are
needed. Shared engine modules and the pinned dependencies are supplied by
the organizer's Manchester-AI-Society/poker_bot runner.

The model implements `seed`, `run`, and `end_game`, uses only its own cards
and public actions, and retains opponent statistics between hands. Runtime
uses the standard library and organizer modules, with no network or file IO.
The pickle uses protocol 4 and the team name is `puhguh`.

The verified baseline is `ContextValueModel`. The exact artifact passed
32,000 hands through real workers with zero faults or timeouts, exact
duplicate mirror ties, and 10,229 source/packed action comparisons without a
mismatch. These checks establish validity; tournament performance remains
uncertain. Checksums are in `PUHGUH_SUBMISSION_MANIFEST.json`.

The latest organizer announcement specifies heads-up play, 400 hands per
round-one match, and the top five teams advancing to 1,200-hand final-round
matches. Stacks reset each hand, with 500 chips and fixed 10/20 blinds.

This standalone submission contains the team's files. To run locally, place
both submission files in a checkout of the organizer's runner and install
its pinned dependencies. No GPU or extra training data is required at runtime.

The shared runner, tests and evaluator are included unchanged from the pinned
organizer revision. The repository therefore supports the organizer's normal
local workflow. A fresh isolated checkout passed all 11 model/API documentation
tests and `python -m submit --team puhguh --out generated`. The regenerated
pickle was byte-for-byte identical to the committed verified artifact.
