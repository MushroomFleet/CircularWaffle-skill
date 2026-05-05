# CircularWaffle

A Claude skill for converting between two registers of English: **plain statements** and **circular waffle** — the rhetorical mode of political speeches, press conferences, corporate statements, and crisis communications.

The skill works in **both directions**:

- **INFLATE**: Turn a direct, economical statement into the kind of weighty, repetitive, sympathy-expanding prose you hear at a podium.
- **DEFLATE**: Take a verbose political or corporate transcript and recover what the speaker actually said, with a repetition analysis that surfaces every reworded restatement.

## Why this exists

If you've ever watched a press conference and thought "that was a lot of words to say very little," you've experienced circular waffle in the wild. Political and corporate speech has a consistent structural grammar — the same seven devices appear again and again — and once you can name them, you can both **produce** waffle on demand and **strip** it away from any source text to see the substance underneath.

This skill makes the rhetorical machinery visible. It's useful for:

- **Writers** drafting fictional politicians, executives, spokespeople, or crisis-response statements.
- **Analysts and journalists** compressing transcripts into their actual content.
- **Speechwriters** stress-testing their own prose against the patterns of professional waffle.
- **Educators** teaching media literacy by showing students how rhetorical inflation works.
- **Anyone** who wants to know what a politician really said in five sentences instead of fifty.

## How it works

Once installed, the skill triggers automatically on phrases like:

- "waffle this up"
- "make this sound like a press conference"
- "write this in the style of a minister"
- "what is this person actually saying"
- "translate this into plain English"
- "cut the politician-speak"
- "deflate this waffle"

It detects the direction (INFLATE or DEFLATE) from context and applies the appropriate transformation.

## The seven inflation devices

The skill is built around seven structural patterns that define circular waffle. Each one can be applied to inflate prose, or identified and reversed to deflate it:

1. **Double-naming** — restate key nouns with a slight elaboration ("an attack... a terror attack").
2. **Triple-rephrase of the call to action** — say "we need to act" three different ways.
3. **Expanding circles of sympathy** — victims → families → loved ones → responders.
4. **Synonym stacking** — "anxiety, of concern" / "security, safety, identity".
5. **Hedge fillers** — "of course", "frankly", "absolutely", "uh".
6. **Restate the obvious** — "and I am absolutely clear about that".
7. **The 'no getting away from' pivot** — frames the substantive point as a forced confrontation.

## Output formats

The skill always shows its working.

**INFLATE mode** produces:

- The inflated prose (paragraph form, no bullets).
- A "Devices applied" block listing which of the seven devices were used, with examples.

**DEFLATE mode** produces:

- A cleaned transcript (disfluencies and timestamps removed).
- A "Plain English" block — typically 20–30% of the original word count, with no loss of substantive content.
- A numbered repetition analysis showing exactly which points were said multiple times and how, with the original-vs-stripped word count delta.

## Example

**Input (5-sentence statement):**

> Thanks for coming on short notice. Last night's attack in Golders Green targeted Jewish people. Our sympathies are with the victims, their families, and the first responders. This isn't an isolated incident — there's been a recent pattern of attacks, and the Jewish community is deeply worried about its safety.

**INFLATE output:**

> Just to say thank you to you all for coming in at short notice for this really important discussion about criminal justice in the aftermath of an appalling attack last night in Golders Green, a terror attack in Golders Green. It is important that we come together very quickly now to take the necessary action. What we saw last night was people being targeted because they are Jewish, and I'm absolutely clear about that. Of course, our thoughts are with the victims, wishing them a speedy recovery, with their families and loved ones, and of course with the volunteers and first responders, who were quite incredible in their response yesterday. But there's no getting away from the fact that this was not a one-off. This has been a series of attacks on our Jewish community, particularly in recent weeks. There is a very deep sense of anxiety, of concern, about security, about safety, about identity, frankly.

≈210 words versus the original ≈50. Same substance, four times the length, and structurally indistinguishable from a real podium statement.

DEFLATE runs the same process in reverse and tells you which devices were applied along the way.

## Calibration principles

The skill follows four rules that keep it honest:

- **Don't sanitise the substance in either direction.** If the input is pointed or controversial, the output preserves that. The skill changes register, not stance.
- **Don't add new content during INFLATE.** Inflation is achieved through repetition and rephrasing of what's already in the input — never by inventing new claims, sympathy targets, or policy commitments.
- **Don't omit substance during DEFLATE.** If a real claim is buried inside a synonym stack or a hedge, surface it. Only strip *redundancy*, not *content*.
- **The commentary block is part of the deliverable.** The skill's value is in making the rhetorical machinery visible. The "Devices applied" or "Repetition analysis" block always ships with the output.

## Installation

Download `CircularWaffle.skill` from this repository and install it in Claude using the skill installer in your Claude settings.

Once installed, the skill loads automatically when you ask Claude to inflate or deflate any text.

## Building from source

The skill is a single `SKILL.md` file packaged as a `.skill` zip. To rebuild from this repo:

```bash
cd skill-creator
python -m scripts.package_skill /path/to/circular-waffle /output/dir
```

## Contributing

Issues and pull requests welcome. If you spot a rhetorical device that recurs in political/corporate speech but isn't covered by the seven, please open an issue with examples — the device list is meant to be empirical, not theoretical.

## License

MIT.

---

## 📚 Citation

### Academic Citation

If you use this codebase in your research or project, please cite:

```bibtex
@software{circular_waffle,
  title = {CircularWaffle: A Claude skill for converting between plain statements and political/corporate waffle},
  author = {Drift Johnson},
  year = {2025},
  url = {https://github.com/MushroomFleet/CircularWaffle-skill},
  version = {1.0.0}
}
```

### Donate

[![Ko-Fi](https://cdn.ko-fi.com/cdn/kofi3.png?v=3)](https://ko-fi.com/driftjohnson)
