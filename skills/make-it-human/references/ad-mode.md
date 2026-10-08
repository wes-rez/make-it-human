# Ad Mode

Ad mode is for ad scripts (UGC, voiceover, talking-head) and ad captions (Meta primary text, TikTok and Reels captions). It runs on top of `rules.md`. Every rule in `rules.md` still applies. This file adds what a human ad writer does that a cleanup pass doesn't: format, rhythm, emphasis, and the persuasion beats.

## When ad mode applies

Turn ad mode on when either is true:

*   The user says the text is an ad, ad script, UGC script, voiceover or ad caption.
*   The user points you at a brand profile.

Otherwise stay in Humanize mode. Don't add beats, line breaks or emphasis to text that isn't an ad.

## Format

*   One sentence or one thought per line.
*   Put a blank line only where the ad moves to a new beat. Don't put blank lines between every line.
*   No headers, bullets, bold or numbering in the ad copy itself.
*   If the profile sets a length limit for the channel, stay under it.

## Rhythm

Human ad copy is uneven on purpose. AI copy is tidy. Make it uneven.

*   Mix line lengths. A long line followed by a three-word line reads human.
*   Fragments are fine ("Huge win for busy parents.").
*   Lines can start with "And", "But" or "So".
*   Use contractions everywhere.
*   Talk to one reader ("you", "your kid"), never "users" or "customers".
*   **Break tidy triads.** "Same genes, same home, just a different start" is a three-beat parallel list, which is an AI rhythm. Make it uneven, cut it to two items, or say it as a plain sentence.
*   **No polished closing tags.** Don't end a line with a neat add-on like "while it matters most", "and that changes everything" or "one step at a time". Stop when the point is made.
*   **No label hooks.** Never open with "Quick fact:", "Here's the thing:" or similar. See Label Hook in `rules.md`.

## Emphasis

Human ad writers push on the one or two things that matter most. Use only the devices the brand profile allows. With no profile loaded, use none.

*   **Caps:** one key phrase in ALL CAPS ("AT HOME").
*   **Repetition:** a doubled word for feeling ("Huge huge win").
*   **Intensifiers and slang:** only the ones listed in the profile's voice notes.

Hard limit: two emphasis moments per ad. Spend them on the product's main benefit or the objection it answers.

## The 8 beats

A persuasive ad usually moves through these beats. Hook comes first and Offer + CTA comes last. Keep the source's order for the beats in between if it works. Otherwise use this order.

| # | Beat | What it does | Test |
|---|---|---|---|
| 1 | Hook | States the claim or tension in the first line | Would the reader stop scrolling at line one? |
| 2 | Proof | Gives a reason to believe the hook: research, a number, a result | Is there something concrete behind the claim? |
| 3 | Mechanism | Explains how it works | Does the reader understand why it works? |
| 4 | Stakes | Says what happens if they don't act | Does the reader feel the cost of waiting? |
| 5 | Product | Brings in the product as the answer to the stakes | Is the product clearly the fix? |
| 6 | Objection handled | Removes the thing that would stop them | Is the biggest "but..." answered? |
| 7 | Who it's for | Names the reader's situation | Would the right reader think "that's me"? |
| 8 | Offer + CTA | Gives the specific action and what removes the risk | Is it clear what to do and why it's low risk? |

The beats are optional. Check for them in ad mode only. If the user says the ad is meant to be short or names the beats they want, check only those.

## Drafting missing beats

When a beat is missing, draft it and mark it inline where it belongs.

*   Mark every drafted line as `[SUGGESTED: ...]` so the user can keep or cut it.
*   Write it in the brand's voice and follow every rule in `rules.md` and this file.
*   Never draft a beat that repeats one already in the ad.

### Claims safety (non-negotiable)

*   **Proof, and any stat, study, number or outcome claim in any beat,** comes only from the source text or the profile's Approved claims list. If neither has one, write a placeholder instead, such as `[proof: source needed]`.
*   **Stakes:** you may describe the reader's everyday experience without a claim ("Dinner turns into takeout again."). Any health, learning, money or development outcome ("kids fall behind", "the gap grows") needs an approved claim. Without one, use `[stakes: approved claim needed]`.
*   **Mechanism and Objection:** use only product facts from the source or the profile.
*   **Offer:** use only offer facts from the profile or source. Never invent "free", a discount, a trial or a guarantee.
*   Never draft anything on the profile's Banned claims list.

### Keep facts exact

Simplify the wording, never the fact.

*   Keep who a study looked at. A study of twins stays a study of twins. Don't widen it to "kids".
*   Keep the strength of a claim. "Linked to" doesn't become "causes", and "most" doesn't become "all".
*   Keep numbers as given. "Almost 2,000" can't become "thousands".
*   If a human version in `examples.md` changed a fact, copy its voice and keep the original fact.

## Output format

Return exactly three parts:

1.  **The ad**, one thought per line, with suggestions marked inline.
2.  **Beats:** one line listing which beats were already there, which you suggested, and which are placeholders.
3.  **Needs from you:** every placeholder and every claim that needs approval. Leave this part out if there are none.

Nothing else. No intro and no explanation of your changes unless the user asks.

## Example (fictional brand)

**Profile facts:** Panfry, a meal kit. Readers are working parents. Approved claims: "Most recipes take 20 minutes." Offer: 50% off the first box. Emphasis allowed: fragments, one caps phrase.

**Input:**
Quick fact: home-cooked dinners are linked to healthier families, and there's research behind it. Panfry delivers fresh, pre-portioned ingredients, chef-designed recipes, and step-by-step cards. It's not just a meal kit. It's dinner, solved. Order today.

**Output:**

Families who eat home-cooked dinners tend to be healthier.
[SUGGESTED: [proof: source needed for the family health research]]

[SUGGESTED: Without a plan, dinner turns into takeout again. And again.]

Panfry sends everything already portioned out.
Most recipes take 20 minutes.
[SUGGESTED: No grocery run after work. No chopping lists.]
[SUGGESTED: Made for parents who get home tired and still want a REAL dinner.]

Get 50% off your first box. Order below.

**Beats:** present: hook, mechanism, product, offer + CTA. Suggested: stakes, objection, who it's for. Placeholder: proof.

**Needs from you:** a source for the family health research, or cut the claim.
