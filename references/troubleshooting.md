# Troubleshooting, Pre-Flight Checklist & Glossary

## Why order matters (parsing priority)

Seedance doesn't read a prompt left-to-right as prose — it weighs blocks by priority.
This is why beautifully written mood copy underperforms blunt technical instruction.

| Priority | Element | Weight | Why |
|---|---|---|---|
| 1 (highest) | `@Reference` tags | very high | face, style, motion — all locked from the reference, overrides text |
| 2 | Technical tail | high | read as hard constraints, not suggestions |
| 3 | Camera instructions | high | named movements override anything implied by prose |
| 4 | Character description | medium-high | the model does not infer — write it explicitly |
| 5 | Scene & location | medium | drives color grade and light simulation |
| 6 | Time-coded beats | medium | sequence is respected but compresses under overload |
| 7 (lowest) | Mood adjectives | low | "epic," "cinematic," "beautiful" — always replace with concrete language |

## Error taxonomy — symptom → cause → fix

| Symptom | Root cause | Fix (add to prompt, EN) |
|---|---|---|
| Face changes through the clip | no identity lock + no technical tail | `Use @Image1 as strict identity reference. Preserve exact likeness throughout. Stable face throughout. No morphing.` |
| Character looks "beautified"/smoothed | model's default aesthetic processing | `No beautification. Preserve exact likeness. No skin smoothing.` |
| Clip ends at 8-10s instead of 15s | too many scene changes, model compresses | cut to 3 beats, one location, one narrative line |
| Camera ignores the instructed movement | movement described in scene text, not as an explicit beat-opener | move it to the very start of the beat: `[0:00-4s] Slow push in.` then action |
| Outfit changes between beats | outfit described once, never reinforced | repeat the key outfit element in every relevant beat |
| Flickering / unstable textures | technical tail missing or incomplete | add full tail + `No flickering. Consistent lighting throughout.` |
| Wrong color grade | palette described vaguely ("dark," "cinematic") | use 3+ concrete color terms: `deep teal shadows, warm amber highlights, desaturated midtones` |
| Inconsistent background | location has no physical anchors | add 2+ surface textures + one fixed architectural element |
| Audio/lip-sync fails | no explicit sync instruction | `Voice and lip sync reference @Audio1 exactly. Match mouth movement frame-accurate.` |
| Prompt cut by moderation | violence / copyright / extreme face close-up | soften: "fight" → "confrontation"; use full-body reference instead of close-up |
| Subject floats / bad physics | tail missing `Realistic physics` | `Realistic physics. Natural gravity. Natural cloth movement.` |
| Slow motion looks wrong | imprecise fps phrasing | `slow motion 120fps` or `250fps extreme slow motion, snap to real-time at [Xs]` |
| Too many events, model confused | overloaded prompt, 5+ scene changes | split into two renders, each one location + one action arc |
| Reference ignored entirely | tag not declared at the start | declare every tag in block 1: `@Image1 — [exact description and usage instruction]` |

## 14-point pre-flight checklist

Run silently before delivering; report a terse pass/fail, full list only on failure
or by request.

1. Every `@tag` declared in block 1 with description + usage instruction
2. Format stated explicitly (16:9 / 9:16 / 1:1) — never assumed from interface defaults
3. Palette has 3+ concrete color terms, not mood adjectives
4. Location names 2+ surface textures
5. Character description covers hair, face, build, and full outfit separately
6. Identity-lock phrase present if a person reference is used
7. Every time-coded beat opens with an explicit camera movement
8. No more than 4-5 beats for a 15-second render
9. No negative instructions ("no dark background") — rephrase positively, the model ignores negations of things not otherwise described
10. No real celebrity names or copyrighted characters
11. Technical tail present, complete, and the literal last line
12. Slow motion (if used) written as `slow motion 120fps`, never "slow mo"
13. If audio is used: lip-sync instruction is explicit and frame-accurate
14. Prompt is one render = one concept, not a 3-act story compressed

## Platform limits

- Max generation length: 15 seconds
- Max images: 9 (`@Image1`-`@Image9`)
- Max videos: 3 (`@Video1`-`@Video3`)
- Max audio: 3 (`@Audio1`-`@Audio3`)
- Recommended beats per render: 4-5 maximum
- Slow motion syntax: `slow motion 120fps` / `250fps extreme slow motion`

## Reference-photo requirements (for `@Image` identity references)

| Parameter | Requirement | Why |
|---|---|---|
| Framing | full-body preferred, waist-up acceptable | close-ups trigger moderation more often |
| Expression | neutral or soft, no extremes | an extreme expression gets baked into every frame |
| Lighting | even, diffused, no hard shadows on the face | hard reference shadows become hard-coded shadows |
| Background | clean, plain or minimal | busy backgrounds interfere with identity extraction |
| Outfit in the reference | matches the shoot, or is explicitly overridden in the prompt | the model tries to replicate the reference outfit unless told otherwise |
| Resolution | minimum 1024px on the short side | low resolution = low identity-lock confidence |
| People per image | one subject only | multiple people in one `@Image` confuses identity |

## Reference declaration patterns

| Use | Declaration line |
|---|---|
| Face/identity | `@Image1 — exact face and identity reference for the main character. Use as strict identity lock throughout.` |
| Full body | `@Image1 — full-body reference for the main character. Preserve exact proportions and likeness throughout.` |
| Style/palette only | `@Image2 — color palette and lighting reference only. Not a character. Apply this visual treatment to the entire clip.` |
| Product/packaging | `@Image2 — exact product and packaging design reference. Do not change, alter, or replace any text, logo, label, color, or design. Must look identical to @Image2 in every frame.` |
| Motion reference | `@Video1 — motion and shot reference. Replicate every shot, camera angle, movement, and transition from @Video1 exactly.` |
| Audio-only video | `@Video1 — audio reference only. Ignore visual content. Use the audio rhythm for timing and cuts.` |
| Music/beat sync | `@Audio1 — music track reference. Video rhythm references @Audio1's beats. Cut on downbeat.` |
| Voice/lip sync | `@Audio1 — voice and lip sync reference. Match mouth movement frame-accurate throughout.` |
| Replace person in base video | `@Video1 — base video. Replace [subject] with @Image1. Keep everything else identical: location, lighting, camera angles, cuts, transitions, background, audio. Only the person changes.` |

## Glossary (EN → what it means)

**Prompt** — the text instruction sent to the model. **Generation/render** — one model
run, up to 15s. **Reference/@tag** — an uploaded file bound to the prompt via `@tag`.
**Identity lock** — the instruction that keeps a character's appearance stable.
**Technical tail** — the fixed constraint block at the end of every prompt.
**Time-coded beat** — a `[0:00-3s]`-style timestamped instruction. **Declaration
rule** — every `@tag` must be declared at the start or it's ignored. **Identity
drift** — a character's appearance subtly changing mid-clip. **Moderation cut** — the
prompt gets rejected for a policy violation. **Depth of field (DoF)** — the in-focus
range; shallow DoF = sharp subject, blurred background. **Bokeh** — the aesthetic of
out-of-focus background light. **Practical light** — a light source visible in frame
(lamp, screen, neon). **Volumetric light** — visible light beams through atmosphere/
particles ("god rays"). **High-key** — bright, overexposed, minimal shadow.
**Low-key** — dark, shadow-dominant. **Morphing** — organic deformation of face/body
geometry. **Ghosting** — a trailing artifact on fast-moving subjects. **Flickering**
— texture/lighting instability between frames. **Compression artifacts** — visual
breakdown from overloading a prompt with too many beats.
