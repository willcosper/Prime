# PRIME Slitter Optimizer

A phone-friendly web tool that turns a trim order into a slitter cut plan: blade layout per pass, how many times each pattern runs, total coil footage, true waste %, pieces by length, and bonus rack stock.

Everything is in `index.html`. Open it in any browser, or host it on any static host (GitHub Pages, Netlify, a shared drive). Nothing to install.

## Shop rules built in

- Same-length batching: pieces cut together share a cut length.
- Six blades: at most 7 strips per pass, counting repeated widths and rack-bonus strips.
- Cut length: ordered length + 3" from 10' to 20' (never past 21'); exactly 21' is cut at 21'. Under 10' and over 21' are cut as ordered.
- Rack stock: leftover exactly 13" or 6 3/4" wide on cut lengths 10'3" to 21'.

## Strategies

- **Option A, rack-stock bonus**: each cut length is its own batch; spare width is slit into 13" / 6 3/4" rack strips where the 7-strip limit allows.
- **Option B, length bonus**: shorter pieces fill spare room in passes at a longer length already on the order, then any remaining spare width can go to rack flats (toggle on the plan). Shown only when it saves coil. Never longer than the longest piece ordered.

Rack flat bonus has two settings on the plan: **Most rack width** (two 6 3/4" where they fit) or **Prefer 13"** (one 13" for every two 6 3/4" possible, which also frees a blade).

The solver minimizes passes per batch (branch-and-bound over maximal patterns with a node limit), then the number of distinct blade setups.

## Editing the color list

The 26 colors live in the `COLORS` constant near the top of the script. Replace the names with the exact names from PRIME's standard, premium and woodgrain charts.
