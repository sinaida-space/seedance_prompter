# Camera & Visual Style Reference

Concrete vocabulary for building `AskUserQuestion` option lists and filling the
prompt template. Seedance weighs exact technical terms far above mood adjectives —
always pull from here instead of writing generic descriptions.

## Camera movement

| Term (use exactly) | Best context | Don't combine with |
|---|---|---|
| slow push in | tension build, emotion, hero product shot | handheld shake (physically incompatible) |
| slow pull back / reveal | scale, melancholy, world intro | tight close-up (nothing to reveal) |
| crash zoom | shock reveal, horror, comedy beat, viral hook | slow motion (tempo conflict) |
| orbital / arc shot | hero presentation, product 360°, fashion | tight interiors |
| tracking shot (side) | walking, chase, movement energy | a static subject (looks wrong) |
| low angle / Dutch tilt | power, dominance, threat | intimate emotional scenes |
| high angle / crane down | vulnerability, scale, world intro | action scenes (too detached) |
| handheld shake | documentary, urgency, raw emotion | beauty / luxury product |
| whip pan | scene transitions, music video cuts | slow emotional moments |
| static / locked-off | tense pauses, art-house, product | boring empty frames |
| snap to real-time | after slow motion, before an impact moment | nothing without preceding slow-mo |
| drone descend | location reveal, epic establishing shot | interiors |
| stabilized tracking | polished follow shots | — |
| robotic arm | mechanical precision, product/tech | — |
| helmet cam / GoPro POV | extreme sports, raw first-person | polished editorial |

**Double-contrast rule for cuts:** every cut should change both shot size *and* camera
behavior. Example: `WS handheld → ECU static → MS crane → CU tracking`.

## Shot sizes

ECU (extreme close-up) · CU (close-up) · MCU (medium close-up) · MS (medium shot) ·
WS (wide shot) · EWS (extreme wide shot)

## Film stock & grain

| Term (use exactly) | Effect | Genre fit |
|---|---|---|
| 35mm film grain, Kodak Portra 400 | warm, organic grain, soft halation | fashion, beauty, editorial, nostalgia |
| 16mm heavy grain, cross-processed | high contrast, color shift, raw texture | horror, indie, music video |
| IMAX digital, no grain | maximum clarity, clinical clean | sci-fi, product, tech, corporate |
| Super 8 film burn, light leaks | vintage warmth, degraded edges, flicker | memory, nostalgia, lo-fi |
| anamorphic lens flares, oval bokeh | horizontal flares, cinematic stretch | blockbuster, sci-fi, action, drama |
| 35mm slide film, Velvia colors | saturated, contrasty, punchy | travel, nature, bright editorial |

## Color grades

| Formula (use exactly) | Genre fit |
|---|---|
| teal and orange grade | action, thriller, mainstream commercial |
| desaturated blue-grey, warm skin tones | nordic noir, drama, horror |
| bleach bypass — crushed blacks, desaturated midtones | war, gritty drama, thriller |
| warm golden hour grade, amber shadows | romance, fashion, beauty, lifestyle |
| neon cyberpunk — magenta, cyan, purple highlights | sci-fi, music video, viral |
| high-key white overexposed editorial | luxury, beauty, minimalist fashion |
| dark moody shadows, single practical light source | horror, noir, psychological drama |

Always give 3-4 *concrete* colors, never a mood word alone — "deep teal shadows, warm
amber highlights, dusty rose midtones" beats "cinematic" every time.

## Surface textures (always include 2+ per location)

polished concrete floor with water reflections · weathered brick wall, peeling paint ·
frosted glass panels with diffused backlight · velvet fabric catching soft directional
light · wet asphalt with neon color reflections · natural stone with moss and deep
shadow · brushed stainless steel, industrial sheen · cracked plaster · water-stained
concrete · matte ceramic · translucent plastic · dusty glass · scratched metal ·
rain-slick pavement · reflective black acrylic · worn parquet floor

## Named cinematographer / director styles

| Style (use exactly) | Result |
|---|---|
| shot on Arri Alexa, cinematic depth of field | professional cinema look, natural bokeh |
| Wong Kar-wai style — shallow depth, motion blur | romantic, melancholic, handheld, motion smear |
| Kubrick one-point perspective symmetry | psychological tension, control, clinical symmetry |
| Roger Deakins naturalistic window light | drama, realism, warm golden window shadows |
| Emmanuel Lubezki long take handheld | immersive, urgent, naturalistic |
| Zack Snyder — slow to fast motion, desaturated | action, graphic-novel, slow-mo transitions |
| fashion editorial — high contrast hard light | fashion editorial, hard rim lighting |

## Special-effect prompt fragments

- **One continuous shot:** `ONE CONTINUOUS SHOT. No cuts. No edits throughout.`
- **Beat-sync montage:** `Format: 15s / [BPM] BPM / [n] shots / beat-synced. Video rhythm references @Audio1's beats. Cut on downbeat.`
- **Match cut:** `MATCH CUT. The same [action] carries seamlessly into [new scene].`
- **Slow motion:** always name exact fps — `slow motion 120fps` or `250fps extreme slow motion, snap to real-time at [Xs]`. Never write "slow mo" or a translated equivalent — imprecise phrasing gives inconsistent results.
