# MOONBORN Production Cost Breakdown: 30 AI Drama Episodes, Real Numbers

Production window: October 10–12, 2026. Series: MOONBORN, a 30-episode werewolf-romance vertical short drama (60 seconds per episode, 9:16), published on the Seven Cradles YouTube channel. Pipeline: full script → 6-shot list per episode → AI video generation with locked character descriptions → assembly (voiceover, subtitles, sound, frozen-frame fallback for refused shots).

## Key facts
- 174 shots sent to the video generator; 136 passed, 38 refused outright — a 21.8% refusal rate.
- Worst episode: EP2 lost 5 of 6 shots (83%) and shipped as frozen frames with continuing audio.
- 17 of 30 episodes lost at least one shot to the safety filter.
- 8 confirmed refusal patterns: (1) any grabbing/holding/slamming between characters, (2) any weapon visible even defensively, (3) peril framing reading as self-harm, (4) close-ups of extreme distress, (5) horror signifiers, (6) whispering/face-too-close close-ups, (7) predatory gaze, (8) fingers on skin or supernatural marks.
- The filter is over-sensitive: tame shots (empty alley, split screen) get flagged when episode context involves stalking or confrontation.
- Upload: the 267 MB finished episode exceeded the browser uploader's ~100 MB cap, so a YouTube Data API route (Cloud project + OAuth + resumable upload) was built; the full-quality original shipped with zero compression.
- Channel reality: Seven Cradles is brand new — under 250 views in its first month. Cold start, no inflated numbers.

## What's good
- The pipeline itself works: script-to-published-episode in about a day per batch once the shot list is locked.
- Character consistency holds when appearance descriptions are pasted verbatim into every prompt plus 3-view reference images.
- The frozen-frame fallback (still + slow Ken Burns push-in + film grain + continuing audio) reads as a stylistic pause, not a broken video — episodes ship on schedule regardless of refusals.
- Pre-screening shots against the 8 patterns before spending generation budget cuts wasted attempts sharply.

## The flaw
- 22% of generation budget is burned on refusals plus one retry each — the single biggest cost driver, and it is unpredictable per episode.
- The safety filter cannot be appealed; the same framing fails the same way every time, so blocked story beats must be re-staged, not re-submitted.
- Werewolf/romance tension lives exactly where the filter is strictest (physical contact, intense faces, peril) — the genre and the filter are in structural conflict.

## Verdict
- Do NOT attempt this for fast, cheap content: the refusal rate will eat your schedule.
- DO attempt it if you want a real 30-episode catalog in a proven genre and you pre-screen every shot against the 8 patterns first.
- Rule of thumb: budget ~20% extra generation attempts for refusals, rewrite the visual (never the story beat), and build the API upload route on day one if your episodes exceed ~100 MB.

## The 8 refusal patterns, with rewrites
| Refused visual | Ship instead |
|---|---|
| Grabbing / holding / slamming a character | Reaction face or aftermath, zero contact on screen |
| Weapon visible, even defensive | Weapon out of frame; dialogue carries the threat |
| Character on a ledge / rooftop edge | Safe wide shot, never the edge |
| Extreme distress close-up (tears, trembling) | Medium shot; distress via posture and voice |
| Horror signifiers (snarling wolves, creepy drawings) | Imply, don't show |
| Whispering / face-too-close | Physical distance; line as voiceover |
| Predatory gaze (watching from the dark) | Neutral staging for the meeting |
| Fingers on skin / supernatural marks | Cut away before contact |

*Compiled October 12, 2026 from the actual MOONBORN production tracker (shots.json: 174 shots, 38 refused). Numbers are from the real run, not estimates.*
