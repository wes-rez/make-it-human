# make-it-human

A Claude skill that rewrites AI-generated or robotic text so it reads like a real person wrote it. For ad scripts and captions, it goes further and writes the way a human ad writer does.

## Two modes

**Humanize** (default) rewrites the text and nothing more. It swaps AI-typical words and phrases for plain ones, removes em dashes, semicolons and mid-sentence colons, cuts paragraphs that restate themselves, drops default hedging, and turns imposed structure back into prose.

**Ad mode** turns on when you say the text is an ad script or caption, or point the skill at a brand profile. On top of the Humanize rules it:

- Formats the ad one thought per line.
- Loosens the rhythm: fragments, uneven line lengths, no tidy three-part lists, no polished closing tags.
- Uses the emphasis the brand allows (caps, repetition), at most twice per ad.
- Checks the ad against 8 persuasion beats (hook, proof, mechanism, stakes, product, objection, who it's for, offer + CTA) and drafts any missing ones inline as `[SUGGESTED: ...]` for you to keep or cut.

It never invents a claim. Proof, stakes and offers come only from your source text or the brand's approved claims. Anything else becomes a placeholder and is listed under **Needs from you**.

## Brand profiles

Brand profiles are kept outside this repo, so the skill can be shared without carrying any client details. Each brand gets a `make-it-human/` folder in its own working folder:

```
<brand folder>/make-it-human/
  profile.md    product, reader, voice notes, allowed emphasis, offer facts, approved and banned claims
  examples.md   AI drafts paired with the human versions that replaced them
```

Ask the skill to set up a new brand and it copies the templates from `skills/make-it-human/templates/` and asks for the essentials.

The skill gets better at each brand over time. Paste a human-edited version of an ad and it saves the pair to `examples.md` and adds one lesson to the voice notes. It copies the human's voice but never their facts. A new claim in a human edit goes on a pending list until you give it a source.

## Layout

```
.claude-plugin/plugin.json                     plugin manifest
.claude-plugin/marketplace.json                lets this repo be added as a marketplace
skills/make-it-human/SKILL.md                  modes, workflows, key rules
skills/make-it-human/references/rules.md       the full word, phrase, structure and punctuation rulebook
skills/make-it-human/references/ad-mode.md     ad format, rhythm, emphasis, the 8 beats, claims safety
skills/make-it-human/references/profiles.md    finding profiles, setting up brands, learning from edits
skills/make-it-human/templates/                blank profile.md and examples.md
```

## Install

In Claude Code:

```
/plugin marketplace add <your-github-user>/make-it-human
/plugin install make-it-human@make-it-human
```

To test locally before pushing, run Claude Code with `--plugin-dir /path/to/make-it-human`.

## Editing

- General writing rules go in `references/rules.md`.
- Ad-specific rules go in `references/ad-mode.md`.
- Anything about one brand goes in that brand's profile, never in this repo.
