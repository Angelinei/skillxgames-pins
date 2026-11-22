# SkillxGames Pinterest batch 01

Free Pinterest automation for SkillxGames, using Pinterest's native bulk Pin upload (CSV) and images hosted in the public GitHub repo [Angelinei/skillxgames-pins](https://github.com/Angelinei/skillxgames-pins).

This folder is the working copy on the box. The live media URLs in the CSV point at raw GitHub files.

- CSV: `pins-batch-01.csv` (30 image Pins)
- Stills: `pins/<universe>/<slug>.png` at 1080×1350 (4:5). Each still is a mid-hold frame from the "new game drop" animation, with the game title on screen.
- Edu Casino games are not included.

Official Pinterest help:

- Bulk upload Pins (CSV format and import path): https://help.pinterest.com/en/business/article/bulk-upload-video-pins
- Sample spreadsheet: https://s.pinimg.com/sub/helpcenter/assets/pinterest-bulk-upload-sample.csv
- Pin specs (image size, file types): https://help.pinterest.com/en/article/review-pin-specs
- Schedule Pins (manual scheduler limits): https://help.pinterest.com/en/business/article/schedule-pins

## Create these boards first (public)

Pinterest can auto-create a board if the name in the CSV does not exist yet, but it is cleaner to create them yourself first (public, with a cover and a short description). Names must match the CSV exactly:

1. Free Brain Games — Quick Games, Memory, Logic, Puzzle, IQ
2. Skillx Valley Games — Skillx Valley
3. Social Media Skills Games — Social Media
4. Learn Money Skills Games — Money Moves
5. Workplace Games — Absurd Bureaucracy / Bureau
6. Pro Skills Games — Pro Skills
7. Adventure Skill Games — Adventure
8. Spot the Scam Games — Social Engineering (public-facing name)
9. Card Games for Sharp Minds — Cards

## How to import the CSV (desktop only)

You need a Pinterest business account. Bulk upload does not work in the mobile app.

1. Log in to your Pinterest business account on a computer.
2. Click the chevron at the top-right to open the menu, then click Settings.
3. In the left-hand navigation, select Import content.
4. Next to "Upload .csv or .txt file", click Upload.
5. Drag and drop `pins-batch-01.csv`, or choose it from the file picker.
6. Wait for the confirmation email. Pinterest may also email you if a row needs to be fixed.

Source for these steps: https://help.pinterest.com/en/business/article/bulk-upload-video-pins

## CSV columns (do not rename)

Header, exactly as in Pinterest's sample file:

`Title,Media URL,Pinterest board,Thumbnail,Description,Link,Publish date,Keywords`

| Column | In this file |
| --- | --- |
| Title (required, max 100 chars) | English, unique per pin |
| Media URL (required) | Public raw GitHub URL ending in `.png` |
| Pinterest board (required) | One of the nine board names above |
| Thumbnail | Left blank (images only; required for video) |
| Description (max 500 chars in the CSV) | English, varied, with a play link in spirit but the click goes through Link |
| Link | The live game page on skillxgames.com |
| Publish date | `YYYY-MM-DDTHH:MM:SS` in **UTC**. Two Pins a day from 2026-11-24 to 2026-12-08, at 09:00 and 16:00 UTC (10:00 and 17:00 Europe/Paris). |
| Keywords | Comma-separated search terms |

## Limits and caveats

- Business account, desktop only, up to 200 images or videos per CSV.
- If a publish date is formatted wrongly, that Pin is not published.
- A date with no time publishes at the same time of day as the upload. A date with a time must be UTC, not Paris time.
- Pinterest's one-at-a-time scheduler is limited to 30 days ahead and 10 scheduled Pins. The bulk-upload help page does not repeat those caps. This batch stays inside 30 days if you upload from 22 November 2026 onward. Upload on 22 or 23 November (Europe/Paris) so the first Pins stay in the future; if a date is already in the past when you upload, that Pin may go live immediately or fail.
- Images are 4:5 (1080×1350). Pinterest also recommends 2:3 (1000×1500) and says Pins taller than 2:3 may be cropped in the feed. 4:5 is shorter than 2:3, so it should display in full. File type PNG, under the 20 MB web limit.
- Near-cream backgrounds can get a faint 4% black overlay in the home feed in light mode (see Pin specs).
- After upload, give Pinterest a little time, then check Scheduled Pins on the profile.
- Claim skillxgames.com on the Pinterest business account if it is not claimed yet, so destination links and analytics behave correctly.
- If Pinterest ever fails to fetch a `raw.githubusercontent.com` image, the Media URL is the first thing to test in a browser (it must open the PNG itself, not a GitHub HTML page).
- Keep this GitHub repository public. Moving or renaming a file will break any scheduled Pin that still points at it.

## Not in this batch

Edu Casino games, seasonal games, and later universes not listed above. The next CSV can reuse the same repo and folder pattern.
