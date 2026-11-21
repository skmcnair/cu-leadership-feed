# cu-leadership-feed

Public JSON feed of U.S. credit union leadership moves (people hired, promoted or retiring, Director/AVP level and up), refreshed each morning from the Credit Union Leadership Moves tracker, for digital signage.

- Feed: `https://raw.githubusercontent.com/skmcnair/cu-leadership-feed/main/moves.json`
- Logos: `https://raw.githubusercontent.com/skmcnair/cu-leadership-feed/main/logos/<slug>.png` (transparent PNG, trimmed; originals in `logos/source/`)
- Wallboard: the `wallboard` branch holds the OptiDev board that reads this feed.

## Fields (one object per move, newest announcement first; all values are strings)

| Field | Meaning |
| --- | --- |
| `move_id`, `sort_date`, `announced` | Stable id, ISO announcement date, display date |
| `name`, `move`, `title`, `level` | Person, Hired / Promoted / Retiring (blank if the source doesn't say), title in the tracker's title style, level (CEO, C-suite, EVP / SVP, VP, AVP, Director, Board) |
| `organization`, `org_short` | Full and short organization names |
| `state`, `region` | Two-letter HQ state; New England, Rest of the Northeast, Midwest, South, West, or National |
| `new_ceo` | `yes` for a CEO-level hire or promotion (these get a spotlight screen) |
| `previous_role`, `previous_title`, `previous_org` | Prior role as written, and split into title and organization where it reads "Title at Organization" |
| `succeeds` | For a new CEO, the predecessor named in the notes, or blank |
| `org_assets` | Total assets (billions at $1B and up, else millions), or blank |
| `effective`, `effective_date` | Effective or retirement date as shown, and as an ISO date when it is one |
| `notes`, `source_url`, `sources`, `found_via`, `added`, `linkedin_url` | Tracker notes, first source link, every source as "Label: url", how it was found, date added, LinkedIn profile if known |
| `logo_url`, `logo_style` | Hosted logo PNG (blank if none found yet); `color`, or `white` (white-only logo: place it on a dark tile) |
