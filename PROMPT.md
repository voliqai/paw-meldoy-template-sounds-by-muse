# Brief for Muse: PawMelody song templates

You are writing **song templates** for **PawMelody**, an Android app that creates
calming lullabies for pets. An AI music model (Eleven Music) turns each template
into a sung song with the pet's real name in it. The owner chooses who sings it:
a studio singer (female or male), or a copy of their own voice.

Your job: write original, calming song templates and save **one Markdown file per
template** in the exact format below. The files are imported automatically, so
follow the format and rules exactly.

---

## 1. What makes a good PawMelody song

- **Purpose:** to soothe a pet in a specific moment: bedtime, being home alone,
  storms or fireworks, car rides, vet visits, new home, an elderly pet resting, or
  simply calm time together.
- **Sound:** slow (55–80 BPM), soft, warm and predictable. Gentle instruments
  (acoustic guitar, piano, harp, strings, music box, soft pads, cello, flute).
  No sudden changes, no heavy drums, no loud builds, no high-pitched sharp
  sounds, no sound effects of barking, meowing, doorbells or thunder.
- **Voice:** soft, close, hushed, lullaby-like; never belted or shouted.
- **Lyrics:** simple, warm, reassuring words a person would say to their pet:
  safety, love, "I'm here", "I'll come back", rest, breathing slowly. Short
  lines, gentle rhymes, lots of repetition (a repeated chorus is good: pets
  respond to the familiar).
- **The pet's name:** written as `{pet}`, exactly like that (curly braces, lowercase).
  Use it **4 to 8 times** per song, mostly in the chorus. Never invent a name.
- **The animal:** a template is written either for one type of animal or for any
  pet. Only mention species details (paws, tail, whiskers, wings, mane, purring,
  barking) when the template is for that species. "Any pet" templates must not
  mention any species-specific body part or behaviour.

## 2. Hard rules (a file breaking any of these is rejected)

1. **Original work only.** Do not copy, translate, adapt or quote any existing
   song, lullaby, poem or melody, including traditional ones such as "Twinkle
   Twinkle", "Brahms' Lullaby" or "Rock-a-bye Baby". Do not imitate a specific
   artist. Never put artist, band or song names in the style.
2. **No health or medical claims.** Nothing like "cures anxiety", "vet approved",
   "clinically proven", "reduces stress hormones" or "treats separation anxiety".
   The songs comfort; they do not treat.
3. **No unsafe or sad content.** No death, illness, loss, abandonment, danger or
   fear in the lyrics. No mention of other people by name.
4. **Section headers** are on their own line in square brackets, for example
   `[Verse]`, `[Chorus]`, `[Bridge]`, `[Interlude]`, `[Outro]`. Use only letters
   and spaces inside the brackets (max 40 characters).
5. **An empty section is instrumental** (header with no lines under it), for
   example `[Intro]` or `[Interlude]`. Use 2 to 4 of them per song: calm
   instrumental moments help pets settle.
6. **Each lyric line is at most 120 characters,** with no blank-line tricks, no
   stage directions like "(softly)", and no chords.
7. **Length:** the app computes the song length from the lyrics:
   - each section with lyrics = (number of lines × 5 seconds) + 2 seconds
   - each instrumental (empty) section = 6 seconds
   - **target: 170 to 180 seconds in total (about 3 minutes); never above 180.**
   Write the computed total in `duration_seconds` and check your arithmetic.
   Example of a 176-second structure:
   `[Intro]` 6 + `[Verse]` 6 lines 32 + `[Chorus]` 4 lines 22 + `[Interlude]` 6 +
   `[Verse]` 6 lines 32 + `[Chorus]` 4 lines 22 + `[Bridge]` 4 lines 22 +
   `[Chorus]` 4 lines 22 + `[Outro]` 2 lines 12 = **176 seconds**.
8. **Language:** all lyrics in the template's language only, natural and
   idiomatic (not translated word for word). Titles in that language too.
9. **No emojis** anywhere in the file.

## 3. Allowed values

| Field | Allowed values |
|---|---|
| `language` | `en` English, `fr` French, `es` Spanish, `de` German, `it` Italian, `pt` Portuguese, `ar` Arabic |
| `species` | `dog`, `cat`, `rabbit`, `bird`, `horse`, `small_pet` (hamster, guinea pig…), `any` |
| `singer` | `female`, `male` (the default studio voice; owners can switch) |
| `moments` | one or more of: `bedtime`, `home_alone`, `storms_fireworks`, `car_ride`, `vet_visit`, `new_home`, `senior_rest`, `calm_time` |
| `mood` | 2 to 4 words, for example: `tender, sleepy`, `reassuring, warm`, `dreamy, peaceful` |

## 4. File format (exactly this)

File name: `<language>-<species>-<slug>.md`, for example `fr-dog-lune-douce.md`.
`slug` = lowercase ASCII letters, numbers and hyphens, unique across all files.

````markdown
---
title: Moonlight Paws
slug: moonlight-paws
language: en
species: dog
singer: female
moments: [bedtime, calm_time]
mood: tender, sleepy
tempo_bpm: 68
duration_seconds: 176
style: gentle acoustic lullaby, soft fingerpicked guitar, warm felt piano, slow 68 bpm, intimate hushed female vocal
description: A slow, warm bedtime lullaby that tells your dog they are safe and loved.
cover:
  prompt: A golden puppy curled up asleep on a soft mossy hill under a glowing crescent moon, starry indigo night sky, dreamy painted storybook style, soft rim light, no text
  palette: midnight navy, lavender, warm peach
---

## Lyrics

```
[Intro]

[Verse]
Hush now {pet}, the day is done
...
```

## Notes

One or two sentences on the intention of the song (why it calms, which moment it suits).
````

Field details:

- **title:** 2 to 5 words, max 60 characters, no quotes, no emojis.
- **style:** comma-separated musical description for the music model: genre,
  instruments, tempo, voice. Max 200 characters. **Never artist or song names.**
- **description:** one sentence shown in the app, max 140 characters, no health claims.
- **cover.prompt:** an image prompt for the song's cover: a calm scene with the
  species of the template (for `any`, a peaceful scene with no specific animal,
  such as a moonlit meadow or a cozy blanket by a window). No text or letters in the
  image, no real brands, no people's faces. Max 300 characters.
- **cover.palette:** 2 to 4 colours that fit the app (dark night tones with soft
  lavender and peach accents work best).

## 5. What to produce

Unless told otherwise, write **24 templates**:

- **English (`en`):** 4 for `dog`, 4 for `cat`, 2 for `any`, and 1 each for `rabbit`,
  `bird`, `horse` and `small_pet`.
- **French (`fr`):** 3 for `dog`, 3 for `cat`, 2 for `any`.
- Cover every moment in section 3 at least twice across all templates.
- Mix female and male singers about half and half.
- Vary the instruments and moods; no two templates should feel alike.

Also write **`INDEX.md`** listing every file: file name, title, language, species,
singer, moments, duration_seconds.

## 6. Final self-check (do this for every file before saving)

- [ ] Front matter has every field, with allowed values only.
- [ ] `{pet}` appears 4 to 8 times, spelled exactly `{pet}`.
- [ ] Every line ≤ 120 characters; headers in `[Brackets]`; 2–4 empty instrumental sections.
- [ ] Computed duration 170–180 seconds and equal to `duration_seconds`.
- [ ] Lyrics fully original, in the template's language, no species words in `any` songs.
- [ ] No artist or song names, no health claims, no sad themes, no emojis.
