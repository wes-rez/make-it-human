---
name: make-it-human
description: Rewrite AI-generated or robotic-sounding text so it reads like a real person wrote it, and write ad scripts and ad captions that sound human and persuade in a brand's voice. Use when the user asks to humanize text, make writing sound natural, remove AI patterns, make text less robotic or avoid AI detection; when they ask to rewrite, fix or finish an ad script, UGC script, voiceover or ad caption; or when they paste a human-edited version of a draft so the skill can learn a brand's voice.
---

# Make It Human

Rewrite AI-generated or robotic text so it reads like a real person wrote it. For ads, go further: write the way a human ad writer does, with the brand's voice, rhythm and persuasion beats.

## Two modes

*   **Humanize** (default). Rewrite the text only, applying `references/rules.md`. Don't add content, beats, line breaks or emphasis.
*   **Ad mode.** Turns on when the user says the text is an ad script or ad caption, or points you at a brand profile. Applies `references/rules.md` plus `references/ad-mode.md`, and uses the brand profile described in `references/profiles.md`.

If you can't tell which mode applies, use Humanize.

## Files

All paths are relative to this skill's folder.

| File | Read when |
|---|---|
| `references/rules.md` | Every run |
| `references/ad-mode.md` | Ad mode |
| `references/profiles.md` | Ad mode, setting up a brand, or the user pastes a human edit |
| `templates/` | Setting up a new brand |

## Humanize workflow

1.  **Analyze the input** for AI patterns at two levels.
    *   Sentence level: em dashes, semicolons, mid-sentence colons, label hooks ("Quick fact:"), formal academic phrases, business jargon, and rhetorical constructions like "It's not X, it's Y".
    *   Document level: paragraphs that restate their opening point, stacked transition words, generic claims with no anchor, default hedging, and imposed structure (bullets, numbered sections, "In conclusion").
2.  **Read** `references/rules.md`.
3.  **Rewrite**, applying every rule. State points directly. Use plain words. Remove every em dash and semicolon. Turn imposed structure into prose. Anchor claims in specifics from the source, and drop hedges the source doesn't need.
4.  **Review** the whole piece against the rules again, at the document level as well as sentence by sentence.
5.  **List placeholders.** If you left any bracketed placeholders for missing specifics, list them after the rewrite.

## Ad mode workflow

1.  **Load the brand profile** following `references/profiles.md`. If there isn't one and the user says to go ahead, say so in one line and run generic.
2.  **Read `examples.md`** for the brand, newest first. Match the voice of the human versions.
3.  **Rewrite** applying `references/rules.md`.
4.  **Apply** the format, rhythm and emphasis rules in `references/ad-mode.md`.
5.  **Check the 8 beats** in `references/ad-mode.md`. Draft each missing beat inline as `[SUGGESTED: ...]`, following the claims safety rules exactly.
6.  **Review** against the Non-negotiables below.
7.  **Return** the three-part output defined in `references/ad-mode.md`: the ad, the beats line, and Needs from you.

## Learning from human edits

When the user pastes a human-written or human-edited version of an ad, save the pair to that brand's `examples.md` and at most one lesson to its voice notes, following `references/profiles.md`. Tell the user in one line what you saved.

## Key Rules Summary

*   **No em dashes, ever.** Use periods or commas, or restructure the sentence.
*   **Colons only after a complete sentence.** Never use a colon to replace an em dash or to set up a label ("Quick fact:").
*   **No semicolons** except in a list whose items contain commas.
*   **Direct statements.** No rhetorical questions, dramatic reveals or "It's not X, it's Y" constructions.
*   **Simple vocabulary.** Replace words like "moreover," "essentially," "leverage" and "cutting-edge" with "also," "basically," "use" and "latest."
*   **Natural flow.** Use "to" instead of "in order to" and "because of" instead of "due to".
*   **No restating.** Don't end a paragraph by repeating its first sentence, or end a piece with a summary of what was already said.
*   **Be specific, never invent.** Ground claims in numbers, names and times from the source. If none exist, leave a bracketed placeholder.
*   **Hedge only when unsure.** Assert directly where the source is confident.
*   **Simplify the wording, never the fact.** Keep who a study looked at, how strong a claim is, and every number as given.

## Non-negotiables

The output fails if any of these happen:

*   A claim, stat, number, offer or outcome appears that isn't in the source text or the profile's Approved claims.
*   A drafted beat isn't marked `[SUGGESTED: ...]`.
*   An em dash appears.
*   A colon follows something that isn't a complete sentence.
*   A fact is changed while simplifying.
*   Ad mode formatting, beats or emphasis are applied to text that isn't an ad.

## Examples

**Example 1: The Big Contrast**
*   **Input:** It's not about working harder—it's about working smarter.
*   **Output:** Focus on working smarter, not just harder.

**Example 2: Overused Descriptors and Em-dashes**
*   **Input:** The vibrant landscape of digital marketing is constantly evolving—therefore, it is essential to leverage cutting-edge tools.
*   **Output:** Digital marketing changes quickly, so you need to use the latest tools.

**Example 3: Formal Academic Phrases**
*   **Input:** It's important to note that this is not an exhaustive list. In conclusion, you should consider these factors.
*   **Output:** Keep in mind that these are just examples. Finally, weigh these factors.

**Example 4: Structural Redundancy and Hedging**
*   **Input:** Creative testing may potentially be one of the most important levers for DTC brands. Brands that test more creatives could see better results over time. Ultimately, creative testing is a key lever for DTC growth.
*   **Output:** Creative testing is one of the biggest levers a DTC brand has. Brands that test more creatives get better results over time.

**Example 5: Label Hooks, Mid-sentence Colons and Semicolons**
*   **Input:** Quick fact: nobody tests the landing page; they only test the ad.
*   **Output:** Nobody tests the landing page. They only test the ad.

**Example 6: Specificity Without Inventing**
*   **Input:** Many brands have seen strong results with this approach.
*   **Output (source gives no specifics):** [Brand name] cut its CPA by [number]% with this approach in [time period].
*   **Placeholders to fill:** brand name, CPA change, time period.

For a full ad mode example, see the end of `references/ad-mode.md`.
