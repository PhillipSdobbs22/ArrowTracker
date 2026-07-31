

Readme · MD
Arrow Tuning Workbook
A spreadsheet-based system (plus a small companion web app) for tracking irregular/budget carbon arrow shafts — their spine, mass, and nock-orientation behavior — so a fleet groups tighter with less trial-and-error, less wasted money, and a hard safety floor before any arrow is shot.

Why this exists
Manufacturer spine ratings assume a shaft is uniform around its circumference. Cheaper or older shafts often aren't. This project treats each arrow's stiffness as something that varies by rotation angle, measures that variation directly, and tracks real shot data by nock orientation — rather than relying on a single spine number and guesswork.

Success is measured by: smaller group sizes, less time tuning by trial and error, less money wasted on unsuitable arrows, no arrow ever shot outside its safe spine/draw-weight range, and going into a match knowing how an arrow behaves instead of discovering it on the line.

What's in this repo
File	What it is
730_rev5_arrow_tuning_workbook.xlsx	The core tool. 14 linked sheets covering spine measurement, mass, shot logging, orientation recommendations, and safety checks.
arrow_tracker.html	A standalone, offline-capable web app for logging shots at the range (arrow ID, spine/mass/point specs, tap-to-plot target, orientation), sized for a phone. Data is stored locally in the browser.
arrow_workbook_master_prompt.pdf	The project's ground rules — objective, scope discipline, and conventions for anyone (human or AI) making changes to the workbook.
Arrow_article_full_SE_revised_R1_editor_clean.pdf	Kuch et al. (2025), "Improving the arrow selection process in archery: the stiffness variation pattern matters," Sports Engineering — the peer-reviewed study this project's spine-variation methodology draws on.
How the workbook fits together
LSI Calculator — Enter 16 spine readings taken around the shaft's circumference (every 22.5°). Produces the mean spine, the variation metrics (LSI-R, LSI-CV, LSI-E), the weak-axis angle, and an ATA-equivalent spine rating.
Mass Asymmetry — A rolling-settle diagnostic test (ordinal: none / clean settle / rocking settle) flagging shafts with a heavy axis, cross-checked against spine data — not folded into any score.
Impact Data / Radar Overlay (16-pt) — Log real shots by distance and nock orientation; overlay spine, impact, and mass patterns on one radar chart (each normalized to its own max, since they're different units).
Cross-Arrow Orientation Study / Summary by Distance — Pooled repeatability (StDev Radius) by orientation across arrows and distances.
Arrow Report Card — Per-arrow summary: best orientation found (from real shots) vs. predicted best orientation (from spine data alone when shots are thin), with an explicit confidence/sample-size gate and a distance-regression slope for extrapolating to untested distances.
LSI & Mass Correlation — Regression checks (with R² and N) on whether spine variation or mass asymmetry actually predicts real group size for this fleet, referencing Kuch et al. (2025) rather than assuming their result transfers automatically.
Arrow Selection (Setup) — Re-ranks the fleet for a specific bow/draw-weight/draw-length combo and flags any arrow outside its safe static-spine range for that setup.
Fleet Forgiveness (Worst-Case) / Control Arrow Diagnostic / Archer Progress Tracker — Supporting views for fleet-wide risk and tracking form/setup drift over time.
Glossary — Plain-language definition of every non-helper column, kept current as sheets change.
arrow_tracker.html is a lightweight field companion for step 3 above — it's not a replacement for the workbook, just an easier way to capture spec and shot data at the range before it gets consolidated into the sheet.

Core principles
Decision-relevant data only. A column only gets added if it changes what the archer actually does (orientation, keep/cull, bow pairing).
No pseudo-precision. Ordinal/diagnostic reads stay ordinal. Predictions are never shown more confident than their sample size supports.
Safety is structural. Any "best arrow" recommendation is checked against spine-vs-draw-weight compatibility first. Static-spine checks are a known floor — dynamic spine (draw length, arrow length, point weight) is an acknowledged, tracked gap, not silently ignored.
Diagnostic ≠ causal. Cross-check metrics (like the mass rolling test) are never treated as proven causal inputs to a model.
In-house measurements are converted, not assumed universal, before being used in any cross-arrow or external comparison.
See arrow_workbook_master_prompt.pdf for the full set of ground rules, including how changes to the workbook should be proposed, logged, and reviewed.

Status
Actively maintained. Open item of note: dynamic spine (accounting for draw length, arrow length, and point weight beyond the current static-spine safety floor) is a known gap, tracked but not yet built.

Background reading
The spine-variation approach is grounded in:

Kuch, A., Laguillaumie, P., Durand, F., Debril, J-F., Monnet, T. (2025). Improving the arrow selection process in archery: the stiffness variation pattern matters. Sports Engineering, 28(1), 8. https://doi.org/10.1007/s12283-025-00487-7


