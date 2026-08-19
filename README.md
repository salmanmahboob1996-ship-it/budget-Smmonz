# budget-Smmonz

Personal budget tracker. One file, no build, no dependencies — open `index.html`
and it runs. Live at
<https://salmanmahboob1996-ship-it.github.io/budget-Smmonz/>.

The salary cycle runs from the 28th to the 27th. Each cycle is created
automatically, recurring lines tick themselves on their due date, and every
account shows a "should have" target that drops as lines are paid and one-off
expenses are added.

## Where the data lives

In this browser's `localStorage`, and nowhere else. The app has no server and
makes no network calls — nothing about your money leaves the phone. The
repository holds no personal detail whatsoever: no amounts, no salary, no
payment names, no dates. A new user builds their own list under Setup; everything
of yours — names, due days, amounts, balances and every past cycle — comes back
from your own `budget.json`, which is never committed.

That also means clearing Safari data, or changing phone, loses it. So the
**Save to my file** button hands the whole database to the iOS share sheet:
choose **Save to Files** and keep one `budget.json` in iCloud Drive. Pick the
same folder each time and it replaces the previous copy. **Load from my file**
reads it back.

iOS gives a web page no way to write to a file on its own, so this step is
manual by necessity. The app counts how many changes have happened since the
last save and nags once they pile up.

## Cycles

Each cycle stores its own copy of its lines and its own salary figures, so
editing the recurring template changes the current cycle onwards and never
rewrites a finished month. Use ◀ / ▶ to move between cycles; any past cycle can
be opened and corrected, and a month with no record yet can be created to
backfill it. Inside a cycle, ✎ edits or deletes a single line — a line that has
been edited stops following the setup table and is marked "changed".

## Keeping it private

The repository is public, and GitHub visibility is per-repository — there is no
way to keep one file in it private. So nothing personal goes in at all: the app
ships blank and `budget.json` stays in iCloud Drive on the phone. `.gitignore`
blocks it from being committed by accident.
