# Data Dictionary

Source: [Baseball Savant Statcast CSV docs](https://baseballsavant.mlb.com/csv-docs), 2025 regular season.

**Prediction-Time Rule**: A column may be used as a feature only if its value is known *before* the target pitch is thrown. Values from *earlier* pitches are allowed (e.g. The previous pitch's type or speed); values from the target pitch itself are not.

## Relevant Columns 
| Name | Category | Description |
|------|----------|-------------|
| `pitch_type` | `target` | The abbreviation type of pitch derived from Statcast. |
| `game_date` | `meta` | Date of the Game. |
| `batter` | `before(ID)` | MLB ID of the batter. |
| `pitcher` | `before(ID)` | MLB ID of the pitcher throwing this pitch. |
| `events` | `after` | Event of the resulting Plate Appearance. |
| `description` | `after` | Description of the resulting pitch. |
| `zone` | `after` | Zone location of the ball when it crosses the plate from the catcher's perspective. |
| `game_type` | `meta` | Type of Game. E = Exhibition, S = Spring Training, R = Regular Season, F = Wild Card, D = Divisional Series, L = League Championship Series, W = World Series |
| `stand` | `before` | Side of the plate batter is standing. |
| `p_throws` | `before` | Hand pitcher throws with. |
| `home_team` | `meta` | Abbreviation of home team. |
| `away_team` | `meta` | Abbreviation of away team. |
| `type` | `after` | Short hand of pitch result. B = ball, S = strike, X = in play. |
| `balls` | `before` | Pre-pitch number of balls in count. |
| `strikes` | `before` | Pre-pitch number of strikes in count. |
| `game_year` | `meta` | Year game took place. |
| `on_3b` | `before` | Pre-pitch MLB player Id of Runner on 3B. (empty if base unoccupied) |
| `on_2b` | `before` | Pre-pitch MLB Player Id of Runner on 2B. (empty if base unoccupied) |
| `on_1b` | `before` | Pre-pitch MLB Player Id of Runner on 1B. (empty if base unoccupied) |
| `outs_when_up` | `before` | Pre-pitch number of outs. |
| `inning` | `before` | Pre-pitch inning number. |
| `inning_topbot` | `before` | Pre-pitch top or bottom of inning. |
| `fielder_2` | `before(ID)` | Pre-pitch MLB Player ID of Catcher.|
| `game_pk` | `meta` | Unique Id for Game. |
| `at_bat_number` | `meta` | Plate appearance number of the game. |
| `pitch_number` | `before` | Total pitch number of the plate appearance. |
| `pitch_name` | `after` | The name of the pitch derived from the Statcast Data. |
| `home_score` | `before` | Pre-pitch home score |
| `away_score` | `before` | Pre-pitch away score |
| `bat_score` | `before` | Pre-pitch bat team score |
| `fld_score` | `before` | Pre-pitch field team score |
| `post_home_score` | `after` | Post-pitch home score |
| `post_away_score` | `after` | Post-pitch away score |
| `post_bat_score` | `after` | Post-pitch bat team score |
| `post_fld_score` | `after` | Post-pitch field team score |
| `home_score_diff` | `before` | Home score minus Away score |
| `bat_score_diff` | `before` | Batting team score less Pitching team score |
| `n_thruorder_pitcher` | `before` | Pitcher times through the order |

## Excluded Columns
- `pitcher_days_until_next_game` and `batter_days_until_next_game` are **future information** (up to 115 days ahead in sample) and must not be used.
- All other ball-tracking (`release_*`, `pfx_*`, `plate_*`, `v*0`, `a*`), batted-ball, and expected-stat columns are post-pitch and excluded.
- `umpire`, `sv_id`, `spin_dir`, `*_deprecated` are empty in 2025 data, therefore excluded. 