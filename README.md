# Monday Screw Count

A one-page form for the weekly colored-screw inventory.

- Count **by size** (pick a size, go color to color), **by color** (pick a color, go size to size), or on the **whole sheet** grid.
- Enter the on-hand count (in boxes) for each color and size. Like the paper sheet: blank = none left, 0 = open box only.
- Anything below its target is flagged with how many to order.
- Click **Copy formatted email** and paste into a new email to management (keeps the table), or **Open in email app** for a plain-text version.
- Under **Colors, sizes & settings** you can rename, add, remove and reorder colors and sizes, and set each size's target. These settings (plus unit and management email) are saved in the browser on that device. The last sent count is shown under each box next week.

Open `index.html` in any browser, no install needed. Edit `src/page.html` and run `./build.sh` to regenerate `index.html`.
