# Brand Profiles and Learning

A brand profile is what makes ad mode sound like one specific brand rather than generic human copy. Profiles never live inside this skill. Each brand keeps its own, usually in that brand's working folder, so the skill can be shared without carrying any client details.

## Profile folder

Each brand has a folder named `make-it-human/` holding two files:

*   `profile.md`: the brand's product, reader, voice notes, allowed emphasis, offer facts, approved claims and banned claims. Template: `templates/profile-template.md` in this skill.
*   `examples.md`: pairs of AI drafts and the human versions that replaced them, newest first. Template: `templates/examples-template.md` in this skill.

## Finding the profile

1.  If the user gives a path, use it.
2.  If the user names a brand, look for `make-it-human/profile.md` in the current working folder, then inside a subfolder whose name matches the brand.
3.  If it isn't found, ask once for the path.
4.  If the user says to go ahead without one, run ad mode generically. Say so in one line ("No brand profile loaded, so this uses generic rules and no emphasis devices.") and use no emphasis devices.
5.  Treat any field still marked `[PLACEHOLDER]` as empty. List it once under Needs from you, and only if this ad depended on it.

## Reading order

Read `profile.md` first, then `examples.md`, newest entry first.

The human versions in `examples.md` are the strongest signal of the brand's voice. Match their line length, rhythm, emphasis and how they talk to the reader. Copy their voice. Don't copy their facts: facts come only from Approved claims and the source text.

If the voice notes and a newer example disagree, follow the newer example and mention the conflict under Needs from you.

## Setting up a new brand

When the user asks to set up a brand:

1.  Create `make-it-human/` in the folder the user names.
2.  Copy both templates into it.
3.  Ask for the four fields ad mode can't run well without: the product, the reader, the offer and CTA facts, and any approved claims with sources. Ask one at a time.
4.  Leave every other field as `[PLACEHOLDER]`. They fill in over time from human edits.

## Learning from human edits

**Trigger:** the user pastes a human-written or human-edited version of an ad that an AI drafted, or says "this is how it should sound".

1.  **Save the pair.** Add an entry to the top of `examples.md` with today's date. Include the AI version, the human version, and three to six concrete bullets on what the human changed. Name the actual lines, not general qualities.
2.  **Save at most one lesson.** If one change would apply to this brand's future ads too, add it as a single line under Voice notes in `profile.md`. Skip it if the voice notes already cover it. If it contradicts an existing note, replace that note.
3.  **Don't learn factual drift.** If the human version changed a fact (widened a study's population, strengthened a claim, changed a number), don't save the changed fact. Note it in the examples entry and tell the user.
4.  **Unapproved claims stay unapproved.** A new claim in the human version goes on the profile's Pending claims list until the user gives a source. It never goes straight to Approved claims.
5.  **Tell the user** in one line what was saved and where.
6.  **No file access?** If you can't write files in this session, print the examples entry and the voice-note line so the user can paste them in.

## What not to save

*   Word choices that only fit one ad.
*   Anything the voice notes already say.
*   General writing rules, which belong in `rules.md` and not in a brand profile.
