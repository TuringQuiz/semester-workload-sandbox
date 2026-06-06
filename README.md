# Semester Workload Sandbox

**Live:** https://turingquiz.github.io/semester-workload-sandbox/

An interactive what-if explorer that shows college students what skipping a
work-day actually does to the rest of their semester. Skip a day and its work
doesn't disappear — it piles onto the days that remain, and because there are
fewer of them each time, the load on each remaining day grows *faster the more
you skip*. The curve is hyperbolic, not linear, and that's the whole point.

It's a single, self-contained HTML file — no build step, no dependencies, no
tracking. Open it in any browser.

## Run it

Open `index.html` in a browser, or visit the live link above.

## What it shows

- **Your semester** — set the work-days in your term, the total cost, and your
  baseline quality hours/day. It derives the total work to absorb and the cost
  per day, each with a short sanity check.
- **Your days** — set how many days you'll skip with a slider, or the 1 / 2 / 3
  days-a-week presets. The week grid (rows of five) fills in to match; the days
  are placed organically — varied each week — since only the *count* drives the
  math, not which specific days.
- **The balloon** — a live, hyperbolic curve of hours/day on the *remaining*
  days as skips increase, with color bands (Comfortable → Getting heavy → Top
  grades at risk → Fantasy zone), a 10-hour ceiling line, and your current
  position marked. Move the slider and watch the marker climb in real time.

## The model

```
total_work             = N (work-days) × baseline_hours_per_day
load_per_remaining_day = total_work / (N − k)        # k = days skipped
```

Defaults assume a full fall/spring semester: ~65 work-days, ~8 focused hours/day
(≈ five courses × ~100 hours each). A summer session is roughly 25 work-days.
Every input is an editable assumption — set them to match your own term.

## Notes

- Pure HTML/CSS/JS in one file; the chart is hand-drawn SVG.
- Typography: Fraunces, Hanken Grotesk, JetBrains Mono (via Google Fonts).
- Deployed with GitHub Pages from the `master` branch — edit `index.html`,
  commit, and push to update the live site.
