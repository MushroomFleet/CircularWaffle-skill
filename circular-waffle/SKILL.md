---
name: circular-waffle
description: Convert plain, direct statements into the circular, repetitive waffle of political/corporate speech — and reverse the process to strip waffle back down to its actual meaning. Use this skill whenever the user asks to "waffle this up", "make this sound political", "add political waffle", "turn this into a politician's statement", "make this sound like a press conference", "write this in the style of a minister/PM/CEO", "deflate this waffle", "strip the waffle out", "what is this person actually saying", "cut the politician-speak", "translate this into plain English", "compress this statement", or any request to either inflate plain prose into circular rhetoric or reduce circular rhetoric back to its core content. Also use when the user provides a transcript and asks for a "real" or "honest" version, or provides a short statement and asks for the "official" or "podium" version. Two modes — INFLATE (plain → waffle) and DEFLATE (waffle → plain).
---

# CircularWaffle

A skill for converting between two registers of English:

- **Plain statement** — direct, economical prose that says a thing once.
- **Circular waffle** — the rhetorical mode of political speeches, press conferences, corporate statements, and crisis communications, where every point is rephrased two or three times, sympathy is expanded into widening circles, and synonyms are stacked for emphasis.

The skill works in **both directions**.

---

## Mode detection

Decide which mode to run before generating output:

- If the user gives a short, dense statement and asks for a "press conference version", "official version", "make this sound political", "waffle this up", "podium version", "minister-speak", or anything similar → **INFLATE**.
- If the user gives a verbose transcript or speech and asks for "what they actually said", "plain English", "stripped down", "cut the waffle", "honest version", "real meaning", or "compress this" → **DEFLATE**.
- If both are plausible, ask the user which direction they want before writing anything.

After generating output, both modes should also include a short **commentary block** explaining which devices were applied (in INFLATE mode) or which redundancies were stripped (in DEFLATE mode). This is part of the skill's value — users want to see the seams.

---

## INFLATE mode (plain → waffle)

The goal is not to make the statement *longer for its own sake*. The goal is to apply the specific rhetorical pattern of political/podium speech, which has consistent structural features.

### The seven inflation devices

Apply these devices to the input. Not every sentence needs every device, but a properly inflated statement should use most of them.

**1. Double-naming.** When a key noun appears, restate it with a slight elaboration immediately after, often as an appositive. The repetition signals weight.
- "an attack last night in Golders Green" → "an appalling attack last night in Golders Green, a terror attack in Golders Green"
- "a budget shortfall" → "a serious budget shortfall, a real fiscal challenge"

**2. Triple-rephrase of the call to action.** The central point ("we must act") is stated three times in slightly different words: a description of the moment, a call to convene, and an assertion about action.
- "We need to act." → "It is important that we come together very quickly now to take the necessary action."

**3. Expanding circles of sympathy.** A single object of concern is expanded into a widening list: the affected person, then their family, then their loved ones, then the community, then those who responded.
- "with the victims" → "with the victims, with their families and loved ones, and of course with the volunteers and first responders"

**4. Synonym stacking.** Pair or triple near-synonyms in a list, separated by commas or "and", to give the sense of weight without adding meaning.
- "worry" → "anxiety, of concern"
- "safety" → "security, safety, identity"

**5. Hedge fillers and verbal cushioning.** Insert "of course", "frankly", "absolutely", "uh", "I mean", "obviously" at the joints between clauses. These signal sincerity-by-effort and buy thinking time.

**6. Restate the obvious for emphasis.** Add a sentence that re-asserts a point already made, framed as a clarification: "And I am absolutely clear about that." or "Let me be clear."

**7. The "no getting away from" pivot.** When moving from sympathy to substance, use a pivot phrase that frames the substantive point as something the speaker is being forced to confront: "But there's no getting away from the fact that...", "We must be honest about...", "The reality is..."

### Structural template for INFLATE

A typical inflated political statement follows this arc:

1. **Thanks/acknowledgement opener** — even one sentence becomes "I just want to begin by saying thank you to..."
2. **The event** — restate using devices 1 and 5.
3. **Call to action** — apply device 2.
4. **Sympathy expansion** — apply device 3.
5. **Pivot to substance** — apply device 7.
6. **The substantive point** — restate using devices 4 and 6.
7. **Trailing emphasis** — close with a synonym stack and "frankly" or similar.

### Output format for INFLATE

Produce two blocks:

```
## Inflated version

[The waffled prose, in paragraph form, no bullet points.]

## Devices applied

- [Device name]: brief example of how it was used here
- [Device name]: brief example
- ...
```

---

## DEFLATE mode (waffle → plain)

The goal is to recover the actual content of a verbose statement and present it economically. This is the reverse of INFLATE — identify each device that was applied and undo it.

### Procedure

1. **Identify repeated points.** Read through and group sentences that say the same thing in different words. Each group collapses to one statement.
2. **Identify expanding circles.** Where sympathy/concern/blame is listed in widening circles, collapse the circle to its essential members (usually one or two).
3. **Identify synonym stacks.** Replace stacks like "anxiety, concern, worry" with a single word.
4. **Strip hedge fillers.** Remove "of course", "frankly", "absolutely", "I mean", "uh", "obviously", "let me be clear", and similar.
5. **Strip restatements of the obvious.** "And I am clear about that" after a clear statement adds nothing — cut it.
6. **Strip the "no getting away from" pivots.** "There's no getting away from the fact that X" becomes "X".
7. **Strip the thanks/opener** unless the user explicitly wants it kept.

The result should typically be **20–30%** of the original word count with no loss of substantive content.

### Output format for DEFLATE

Produce three blocks:

```
## Cleaned transcript

[The original prose, with disfluencies removed and timestamps stripped, but otherwise intact. This is the readable version.]

## Plain English

[The actual content, stripped down. Usually one short paragraph or 2-3 sentences.]

## Repetition analysis

The speaker made the same point N times by rewording or rephrasing:

1. [Point]: [list of how it was restated]
2. [Point]: [list of how it was restated]
...

[Brief summary: original word count vs. plain English word count.]
```

---

## Examples

### INFLATE example

**Input:**
> Thanks for coming on short notice. Last night's attack in Golders Green targeted Jewish people. Our sympathies are with the victims, their families, and the first responders. This isn't an isolated incident — there's been a recent pattern of attacks, and the Jewish community is deeply worried about its safety.

**Output:**

## Inflated version

Just to say thank you to you all for coming in at short notice for this really important discussion about criminal justice in the aftermath of an appalling attack last night in Golders Green, a terror attack in Golders Green. It is important that we come together very quickly now to take the necessary action. What we saw last night was people being targeted because they are Jewish, and I'm absolutely clear about that. Of course, our thoughts are with the victims, wishing them a speedy recovery, with their families and loved ones, and of course with the volunteers and first responders, who were quite incredible in their response yesterday. But there's no getting away from the fact that this was not a one-off. This has been a series of attacks on our Jewish community, particularly in recent weeks. There is a very deep sense of anxiety, of concern, about security, about safety, about identity, frankly.

## Devices applied

- Double-naming: "an appalling attack... a terror attack in Golders Green"
- Triple-rephrase of call to action: "important discussion / come together quickly / take the necessary action"
- Expanding circles of sympathy: victims → families → loved ones → volunteers → first responders
- Synonym stacking: "anxiety, of concern" and "security, safety, identity"
- Hedge fillers: "of course", "frankly", "absolutely"
- Restate the obvious: "and I'm absolutely clear about that"
- "No getting away from" pivot: introduces the substantive claim about a pattern

### DEFLATE example

**Input:** (the inflated text above)

**Output:**

## Plain English

Thanks for coming on short notice. Last night's attack in Golders Green targeted Jewish people. Our sympathies are with the victims and the first responders. This isn't an isolated incident — there's been a recent pattern of attacks, and the Jewish community is deeply worried about its safety.

## Repetition analysis

The speaker made the same point roughly five times by rewording or rephrasing:

1. The location and nature of the attack: "appalling attack in Golders Green" / "terror attack in Golders Green"
2. The need for action: "important discussion" / "come together quickly" / "take the necessary action"
3. Sympathy: "victims" / "families" / "loved ones" / "volunteers" / "first responders" (overlapping categories)
4. Concern: "anxiety" / "concern"
5. Stakes: "security" / "safety" / "identity"

Original ~210 words → plain version ~50 words (≈24% of original).

---

## Calibration notes

- **Don't sanitise the substance in either direction.** If the input says something pointed or controversial, the output should preserve that. The skill changes register, not stance.
- **Don't add new content during INFLATE.** Inflation is achieved by repetition and rephrasing of what's already in the input — never by inventing new claims, new sympathy targets, or new policy commitments.
- **Don't omit substance during DEFLATE.** If a substantive claim is buried inside a synonym stack or a hedge, surface it. Only strip *redundancy*, not *content*.
- **Match the input's domain.** Political speech sounds different from corporate-earnings-call speech, which sounds different from academic-conference speech. The seven devices apply to all of them, but lexical choice should match the source register.
- **The commentary block is part of the deliverable.** Users find this skill useful precisely because it makes the rhetorical machinery visible. Don't skip it.
