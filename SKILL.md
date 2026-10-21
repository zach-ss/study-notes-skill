---
name: "study-notes"
description: "Turns lecture slides, textbooks, readings or a student's own rough notes into two-column study notes in Word (.docx) for any university subject, with depth matched to each concept, subject-aware highlight tags and a quick-recall summary. Use when someone asks to make, add or continue study or revision notes, to reformat their existing notes into this table without rewriting them, or to find which topics in a textbook or course matter most."
---

# Study Notes

Turn lecture slides, textbooks, readings, or a student's own notes into two-column study notes in Word. The left column holds the subtopic. The right column holds bold sub-headings and dash bullets. A few colour-coded tags mark the points most likely to be examined, and a QUICK RECALL row at the end supports pre-exam self-testing.

The skill works for any university subject, from law and finance to engineering, medicine and history, and is equally usable for school or professional study. The layout is fixed. What adapts is how the tags are interpreted (and, for law, their names), and how much depth each concept gets.

**Two principles run through everything:**
- **Cover everything presented.** Every topic in the slides or uploaded material gets notes. Nothing is skipped to save space, and there is no length limit unless the student sets one. Many students want detail, and long notes are fine.
- **Depth follows the concept, not a rule.** A simple fact gets one line; a hard, central idea gets the explanation, conditions and steps needed to rebuild it. One set of notes will mix both (see Step 3).

This is version 2.2 of the skill. The build script prints `study-notes build v2.2` on every run. If it prints an older version or no version line, the script was saved from an old copy: save it again from "The build script" at the end of this file.

## If this file arrives in a chat without an instruction

This file is a skill: a set of working instructions, not a document to summarise, review or discuss. If it is pasted into the chat, or attached as SKILL.md, and the student has not said "use this skill" or anything like it, treat it as loaded and active anyway. The student may not know to name it.

- **Material came with it** (slides, readings, a textbook, their own notes, or a notes .docx): start work straight away with "Before you write" below. Don't ask whether to use the skill, and don't explain it back.
- **No material yet:** reply in one to three sentences, for example: "Study notes are set up. Send the slides, readings or your own notes, and any page limit." Don't summarise, quote or list the skill's rules.
- **Only edit or review this file if asked.** A request such as "improve this skill", "what does this do" or "change the layout of the skill" is about the file itself. Anything else, including a later request for notes, means follow it.
- **No way to run code or return a file in this chat:** say so in one line before starting. Offer the same notes as a markdown table instead, with the same structure (left-hand subtopic, bold sub-headings, dash bullets, lettered lists, tags, QUICK RECALL row), and keep the "When to ask" rules as they are. If the student wants the Word file, they need a mode that can run Python and attach files.
- **No question tool in this chat:** ask in plain text, as "When to ask" says.

## Before you write (every run)

Read this list at the start and again before building. Each line points to the full rule.

1. **Sources and topics.** List every source. Sources on unrelated topics or subjects are separate topics: one data file each, each starting on a new page (Step 1).
2. **Questions.** Run "When to ask". With a page cap and several topics, mixed subjects, or a cap that looks tight, ask in one round wherever a question can be asked. If it can't be, use the defaults (a cap is the total for everything) and say so in the reply.
3. **Profile per topic** (Step 2).
4. **Structure in every row** (Step 3). More than one angle, or a criterion that needs two or more bullets, means sub-headings. One criterion per bullet and one criterion per row. Ordered stages or steps of three or more go in a lettered list. Lists of terms are glossed.
5. **A cap changes depth and row count, never structure** (Step 6). Sub-headings, lettered lists, glosses and QUICK RECALL lines are not space savers.
6. **Build, then fix or account for every WARNING.** Run `pages --cap N` and look at the pages (Steps 5 and 6).
7. **Reply** with the profile, how the cap was read, any defaults used, framing-line rows, accepted warnings and discrepancies (Step 7).

## Modes

| Mode | When | What happens |
|---|---|---|
| **Generate** (default) | Slides, a textbook, readings, and a request for notes | New notes written from the material |
| **Append** | An existing notes .docx plus new material | A new topic is added in the existing document's format |
| **Reformat** | The student's own notes or ideas, with a request to tidy, format or "put into the table" | Their words are kept and only restructured |
| **Reformat + fill** | The student's notes plus slides, with a request to fill gaps | Reformat, then add missing content marked ADDED |
| **Prioritise** | A textbook or course materials, and a question like "what should I focus on?" | A ranked list of topics in the reply, no document (see "Prioritise mode") |

If the request could mean more than one mode, ask (see "When to ask").

## When to ask

Ask about any unknown that would change what gets built (how many documents, how a cap applies, which labels, which mode, what to cut) wherever a question can reasonably be asked. Don't guess silently at those. Don't ask about things you can check yourself or that have a sensible fixed default (see "Don't ask about").

**Rules**
- **One round, after a quick look, before writing.** Skim the sources first (titles, contents, subject) so the questions can name real topics. Then ask everything in a single round of at most 4 questions and build without stopping. Anything that comes up later (source errors, gaps, conflicts that don't change the structure) is reported at the end, not asked mid-run.
- **Use selection boxes when available.** If a multiple-choice question tool exists, use it: 2 to 4 options per question, the recommended option first and marked "(Recommended)", and multi-select where several answers can apply. The student can always type their own answer. With no question tool, ask in plain text with the defaults stated.
- **Write the questions for this material.** Wording and options come from what was uploaded, for example real topic names found in the slides. The tables below are guidance, not a fixed form.
- **If nobody can answer** (an unattended or scheduled run, or no reply), use the defaults below. Say in the first line of the reply which defaults were used, and offer to redo it. Never stop and wait.

**Always ask when the situation arises**

| Situation | Question | Options (recommended first) | Default if unanswered |
|---|---|---|---|
| A page cap and two or more topics or sources | "Is [N] pages the total for everything, or [N] per topic?" | Total for everything (Recommended) / Per topic | Total for everything |
| Sources on unrelated topics or from different subjects | "One Word document with each topic on a new page, or a separate document per topic?" | One document, new page per topic (Recommended) / Separate documents | One document, new page per topic |
| The cap looks tight for the material (roughly more than six subtopics per capped page) | "To fit [N] pages, should I keep every subtopic with less depth on the minor ones, or drop [X, Y]?" | Keep every subtopic, less depth (Recommended) / Drop the named ones | Keep every subtopic, less depth |
| The input could mean two modes | "You've given me your notes and the slides. What should I do?" | Reformat and fill gaps / Reformat only / Write fresh notes from the slides | The most literal reading of the request |
| The subject is unclear or mixed (for example commercial law) | "Which tag labels suit these notes?" | Law labels / Generic labels / No tags | The profile from Step 2 |

**Ask when it would change the result**

| Ask when | Example question | Typical options (default first) |
|---|---|---|
| A large or very dense source, and the student hasn't said how detailed | "How detailed should these be?" | Standard / Rich / Lean |
| A textbook with no unit outline, tutorial sheets or past papers, and it's unclear what matters | "Do you have the unit outline, tutorial sheets or past papers? They show what's examined." | No, use what I've given / Yes, I'll upload them |
| Many topics, and the student may want emphasis | "Any topics you want in extra depth?" (multi-select) | The 2 or 3 likeliest heavy topics found, plus the automatic free-text option |
| Slides and textbook conflict on something structural | "Which should I follow?" | Show both / Slides / Textbook |

**Don't ask about:**
- Scope. The default is everything presented.
- Whether there is a page cap, or what length the student would like, when none was given. (How a stated cap applies is a different question, and is asked above.)
- Anything checkable, such as arithmetic errors in slides. Check it and report it.
- Formatting, tag style or the key line, unless the student raises them.

## Step 0: Set up the build tool

Save the script in "The build script" at the end of this file as `study_notes_build.py` in the working directory, once per session. It needs only Python 3, with no packages. Always build the document with this script rather than hand-writing Word XML or using another library: the script enforces the house style (fonts, sizes, colours, widths, numbering, row breaking), warns about tagging, structure and list problems, and prints its version on every run.

## Step 1: Gather the inputs

- **Find every source.** Look in the attachments and the working folder for slides, textbooks or readings, a unit outline, tutorial sheets, past papers, the student's own notes, and an existing notes document. Do not assume any particular folder layout.
- **Read every page of the slides.** Many PDF readers limit pages per call, so read in batches until done. Never skip pages. If slides are mostly images or diagrams, render pages to images and look at them.
- **Textbooks and readings:** use them unless the student says slides only. For a whole textbook, build a concept map first (Step 2b) and read the relevant chapters in full. Readings restore detail the slides compress and show which example or authority is the leading one.
- **Existing notes document:** run `python3 study_notes_build.py inspect --doc "<file>.docx"`. It reports column widths, the tag labels in use, whether a key line exists, existing topic headings (to number the next topic), and fonts.
- **The student's own notes (reformat):** for a .docx, run `extract`, which keeps their bold, italics and highlighting as markup. Read .md and .txt directly, use pasted text as given, and read PDFs as usual.
- **Several decks for one topic:** merge them into one topic with a title naming both. Merge only sources that cover the same topic.
- **Unrelated sources** (different topics or subjects): keep them as separate topics. Write one data file per topic. `build` the first, then `append` each of the others with `"new_page": true` (and `"key_line": false`), so each topic starts on its own page under its own title. Make separate documents instead if the student chose that.

## Step 2: Resolve the subject profile

The profile sets how tags are interpreted, the citation style, and the label set. Resolve it in this order and stop at the first that settles it:

1. **What the student said** (unit name, subject, "these are law notes").
2. **An existing notes document.** Its label set (from `inspect`) wins, and its layout is matched.
3. **Signals in the material** (see the table below).
4. **Ask** (see "When to ask"). If nobody can answer, use the closest profile with generic labels and say so.

State the result in one line at the top of the reply, for example: "Profile: engineering; generic labels; standard depth." The student can then correct it. When topics differ in subject, resolve the profile for each topic separately and give one profile line per topic.

| Family | Typical signals | KEY | METHOD | ★ EVIDENCE | APPLY | Style notes |
|---|---|---|---|---|---|---|
| **Law** | Case citations ("v", "[2019] HCA 1"), statute sections ("s 51"), courts, "held", "ratio", "obiter" | Statutory provision or black-letter rule | Test, elements or factors a court applies | Leading case | Policy rationale or strategic point | Case names italic with citation; sections as "s 12(3)" |
| **Business, finance, economics, accounting** | $ figures, rates, formulas, models, accounting standards | Formula, definition, standard | Procedure, decision rule, conditions of validity | Real data, market or historical example | Interpretation, pitfall, practical use | Formulas with real superscripts; cite standards by number |
| **Maths, statistics, physical sciences** | Theorems, derivations, equations, units | Law, theorem, equation, definition | Derivation or proof steps, solution method, assumptions | Landmark experiment or standard example | Limitation, common error, where used | Always give units; long central equations on their own line |
| **Engineering and computing** | Design equations, standards, code, algorithms, complexity | Design equation, definition, specification | Algorithm, design or analysis procedure | Case study, failure, benchmark | Trade-off, constraint, safety factor | Code kept to short inline identifiers |
| **Life and health sciences, medicine** | Mechanisms, pathways, anatomy, drugs, trials, normal ranges | Definition, mechanism, normal value | Diagnostic criteria, procedure, classification | Landmark study or trial (Author Year) | Clinical relevance, contraindication, exam pitfall | Generic drug names; values with units |
| **Social sciences, psychology, education** | Theories, studies, frameworks, research methods | Theory or concept definition | Framework, model, research method | Key study (Author Year) and its finding | Critique, application, implication | Cite as (Author Year) |
| **Humanities** (history, philosophy, literature, arts) | Arguments, texts, periods, thinkers, quotations | Thesis, concept, date or event to know | Interpretive lens, structure of an argument | Key source, quotation or work | Significance, critique, debate | Short quotes in curly quotes, attributed; works italic |
| **General / other** | None of the above | Must know | How to apply | Leading example or source | Practical point | Plain |

### Law labels

When the profile is law, use the law label set (`"label_set": "law"`): RULE, TEST, CASE and POLICY replace KEY, METHOD, EVIDENCE and APPLY. Colours, sizes and meanings do not change.

- Use law labels when the student says the subject is law, or when legal signals dominate the material.
- For mixed subjects (commercial law in a business degree, regulation, business ethics, health or planning law), ask: law labels or generic labels?
- When appending, the labels already in the document override detection.
- A student instruction always wins, in either direction.

## Step 2b: Build a concept map (textbooks and multi-source topics)

When there is a textbook, several sources, or a large topic, build a short concept map before writing. It is the input to depth calibration in Step 3 and to prioritise mode. Keep it in a working file (for example `concept_map.md`) and reuse it for later topics from the same unit in the session.

**Read in stages, not cover to cover.** Start with the contents, learning objectives, chapter summaries, key-term lists and index. Then read in full the chapters that match the slides or the student's request. Say briefly what is being read when a book is long.

**For each concept, record weight and difficulty from these signals:**

| Signal | Suggests |
|---|---|
| Covered in the slides, unit outline, tutorial sheets or past papers | High weight; course materials are the strongest evidence and override the textbook |
| Long section, several worked examples, many end-of-chapter problems | High weight |
| In the learning objectives, chapter summary, a key-equation box or the glossary | High weight |
| Referred back to later ("recall from Chapter 3"), or a prerequisite for later topics | High weight (foundational) |
| Lecturer emphasis ("note that", "this is important", "exam") | High weight |
| Several steps, conditions or assumptions; a long derivation; dense equations | High difficulty |
| A known trap: sign conventions, units, "valid only if", easily confused pairs | High difficulty |
| In the textbook but absent from the slides and other course materials | Lower weight (still covered if the student uploaded it for notes) |

Rate each concept high or low on both. The map is a judgement, not a fact: say in the reply which concepts were treated as heaviest so the student can correct it.

## The tagging system

Every tag has a fixed colour and meaning in every subject. The data file may use either the generic or the law name; `label_set` decides which name is printed.

| Code | Generic label | Law label | Colour | Meaning |
|---|---|---|---|---|
| KEY | KEY | RULE | 1F4E79 dark blue | Something to state from memory: rule, formula, definition |
| METHOD | METHOD | TEST | 6A3D9A purple | How to apply or decide: test, steps, criteria, conditions |
| EVIDENCE | EVIDENCE | CASE | B45309 amber | The single leading authority or example, always with a gold ★ (B8860B) and a yellow highlight |
| APPLY | APPLY | POLICY | 2F6F4E green | The key practical consequence, pitfall, critique or policy point |

Tag labels are bold, coloured and 10pt; body text is 11pt; the ★ is 11pt.

**Tag sparingly. This is the most important tagging rule.** Aim for roughly one tagged bullet per two or three plain ones. A row may have no tags at all. A short row (three or fewer bullets) carries at most one tag. One tag per bullet at most, and sub-bullets are never tagged. Detailed notes do not mean more tags: a deep row gets more plain explanatory lines, not more highlights. The test: would a student revising the night before the exam want this line highlighted?

For each bullet, work down this list and stop at the first yes:

1. Is it the single most important authority or example for this subtopic? Then ★ EVIDENCE (`"star": true`). Only one per subtopic. Other examples and cases stay plain (case names still italic).
2. Is it something the student must be able to state from memory (the core rule, formula, law or definition)? Then KEY. Only the one or two central ones per subtopic, not every definition.
3. Is it how to apply or decide something (a test, steps, criteria, the conditions under which a formula holds)? Then METHOD.
4. Is it the single most important practical consequence, pitfall, critique or policy point? Then APPLY.
5. Otherwise it stays plain.

KEY is what is true; METHOD is how to do or decide. In finance, for example, "PV = PMT / i" is KEY, "valid only if i > g" is METHOD, "price and yield move inversely" is APPLY, and the historical consol prices are the ★ EVIDENCE.

**When tags don't fit:**
- Never force a tag. A bullet that fits none stays plain, and leaving a tag unused for a whole subject is fine.
- If tags fit the material badly overall (studio practice, language vocabulary lists, workshop notes), or the student asks, use tagless mode (`"tagless": true`). It keeps bold lead terms, sub-headings and QUICK RECALL, with no tags and no key line.
- Student overrides always win: "no tags", "tag more", "tag fewer", law labels in another subject, or custom label wording (`label_overrides`). Custom wording changes only the printed name; colours and meanings stay.

**Key line.** A one-line legend under the title shows the active labels and their meanings. It is on by default for new documents. Turn it off (`"key_line": false`) when appending to a document that already has one (`inspect` shows `has_key_line`), or when the student asks.

## Step 3: Plan the rows and calibrate depth

### Rows

- **One row per subtopic.** The left label is 2 to 5 words, bold, and understandable at a glance. Cover every subtopic in the material.
- **Sub-headings.** In the right cell, use bold sub-headings whenever a row covers more than one angle or more than one classification criterion (for example "Definition", "Derivation", "Application"). Bold-lead bullets (`**Breadth** (Table 3-5): …`) are fine when each criterion fits in one bullet. When any criterion in the row needs two or more bullets, give each criterion its own sub-heading instead. Never put several criteria in one bullet ("Aims: … Level: … Breadth: …"); the script warns on this. A row of five or more bullets needs sub-headings. Sub-headings are the first fix for a row that reads as a clunky run of bullets. The script adds the blank line between groups.
- **No bare lists.** A bullet that is only a string of names gives the student nothing to recall. Gloss each item that matters in a few words, in brackets, or split the list under a sub-heading. The script warns on bare lists and on lists of short terms that are mostly unexplained. A list introduced by "e.g." is illustrative and needs no glosses.
- **One criterion, one row.** Don't stack unrelated criteria in a single row to save space (for example demand stability inside an "object" row). If a row label can't name everything in it, split the row or rename it.
- **Definition lists:** bold the lead term, then " – " and the explanation, instead of tagging.
- **Ordered stages, chronologies, steps or elements** of three or more: use a lettered list (`l` items), not an arrow chain or a comma run. Each group restarts at (a). The script warns on an arrow chain of four or more steps in a row with no lettered list.
- **Equations:** use real symbols (×, −, ÷, ≤, ≥, ≈, Σ, √, ∞, →, Greek letters) with `^{}` for superscripts and `_{}` for subscripts, for example `FV = PV(1 + i)^{n}` and `CF_{t}`. Put a long equation that reads badly inline on its own `eq` line beneath the bullet that explains it; tag the bullet, not the equation line. Always give units where they apply.
- **Citations:** follow the profile's style. Include only authorities, studies and figures that appear in the provided materials. General knowledge may explain a point but must never introduce new citations.
- **No repeats:** do not repeat content already covered in an earlier topic of the same document.
- **Title:** follow the document's numbering ("Topic 4: …", "Week 7: …"); `inspect` lists the existing headings. For a new document, use the lecture's own title.
- **QUICK RECALL:** draft one condensed sentence per subtopic while the row is fresh. Closely related rows can share a line, but every list the student must be able to recite (traits, types, stages, steps) needs its own line. Don't merge rows away to save space unless a page cap forces it. The script warns when there are fewer lines than about three quarters of the rows.
- **Nothing else goes in the document:** no introductions, no source lists, no topic-level overview line under the title, and no legend beyond the key line, unless the student asks.

### Framing lines (default: none)

A framing line is one italic sentence with no bullet, at the very start or end of a row. It fixes one problem: a row that reads as a run of bullets with no sense of how they fit together. Most rows never need one, and a topic with none is normal.

**Try these first, in this order:** a sub-heading, bold lead terms, then a tagged bullet. Use a framing line only when none of them does the job.

**An opening line is allowed only when one of these is true:**
- the row has five or more parallel top-level bullets, and sub-headings would leave one-bullet groups;
- the first bullet cannot be understood without a premise;
- the row's sub-headed parts contrast, compete or build on each other in a way the headings alone don't show (for example, two rival chronologies).

**A closing line is rare.** Use one only for a consequence that no bullet in the row states and the QUICK RECALL line doesn't already carry.

**The deletion test.** Delete the line. If the student can still see how the bullets relate, leave it out. Framing lines take this test instead of the cut test, which is built for content lines.

**Form**
- One sentence, 25 words or fewer, in plain words.
- Never tagged or starred. If the line is a rule to memorise, it is a tagged bullet instead.
- No stock openings ("In summary", "Overall", "Key takeaway", "In short").
- Doesn't restate the row label, a bullet, or the QUICK RECALL line.
- In the data file: `{"p": "…", "frame": "open"}` as the first item (or the first item after a sub-heading), or `{"p": "…", "frame": "close"}` as the last item. The script sets it in italics and keeps an opening line with the text below it.

**Limits**
- At most one opening and one closing line per row, and both together only in a row marked `"depth": "deep"`.
- None in a row with three or fewer top-level bullets, and no opening line in a row whose first bullet is already a KEY statement.
- No more than about one framed row in four across a topic, rounded up. The script warns above one in three. These are ceilings, not targets.
- Framing lines never count as coverage, and they are the first thing cut under a page cap.
- In the reply, name the rows that got one, so the student can veto them. The build prints the list.

### Depth calibration

Decide each concept's depth from its **weight** (how much it matters) and **difficulty** (how hard it is to rebuild from a short note). Use the concept map when there is one. Otherwise judge from the slides: slide count and time spent, worked examples, lecturer emphasis, steps and conditions involved.

| Weight | Difficulty | Treatment | Example |
|---|---|---|---|
| Low | Low | One short line | A naming convention, a minor definition |
| High | Low | One tagged line, plus a sub-bullet of context if it helps | A core formula and when it applies |
| Low | High | Two or three lines: what it is and when it is used | A supporting derivation the lecturer moved through quickly |
| High | High | Full treatment (below) | The central derivation, design method or legal test |

**Full treatment** for a high-weight, hard concept, as much of this as the concept needs:
- the core statement (tagged), then indented sub-bullets for **why** it holds or matters;
- the **conditions or assumptions** under which it applies, and what breaks when they don't;
- **steps** as a lettered list, for a procedure, derivation outline or multi-element test;
- the central **equation** on its own line, with symbols and units defined;
- the **inputs and result** of one worked example, if the material has one;
- the **common error** or easily confused neighbour.

Mark such rows `"depth": "deep"`; the script warns if a deep row ends up thin. Long bullets that carry one hard idea may run past 18 words; mark them `"dense": true`. Use `"sub": 2` for a second indent level when a sub-point needs its own detail.

**Two tests on every row:**
- **Reconstruction test** (high-weight concepts): could a student who missed the lecture rebuild this from the note alone, well enough to answer an exam question on it? If not, add the missing step, condition or "why" as a sub-bullet.
- **Cut test** (every content line): does this line carry a tag, help rebuild a high-weight concept, or state a low-weight fact in one line? If none, cut it. This keeps detailed notes from bloating. Framing lines take the deletion test instead (see "Framing lines").

**Density dial.** The default is **standard**, which uses the table above.
- **Rich:** gives low-weight concepts their context too and includes every worked example.
- **Lean:** reduces high-weight concepts to the statement, conditions and steps, and low-weight ones to a line or nothing beyond a mention.
- If the student names concepts they want in depth, those get full treatment regardless of the map.

Short lines remain the default for simple material. Depth is earned by weight and difficulty, not applied evenly.

## Step 4: Verify

- Recompute every number in the material that can be recomputed (worked examples, formula outputs, totals, unit conversions) by running code, not mentally.
- Check internal consistency. Look for the same figure stated two ways, or a label that does not match its figures (for example a "151st payment" whose figures belong to payment 181).
- Check that the source's prose and its tables or figures agree (for example a table listing micro, macro, international and global while the text names local, national, regional and global). Treat a mismatch like a numerical error: note it in a sub-bullet and list it in the reply.
- **If the source is wrong,** use the correct figure and add a sub-bullet: "Slide shows X; recomputed Y. Check with your lecturer." List each discrepancy in the reply. Never silently correct an error and never silently copy one.
- **In reformat mode,** run the same checks but only report problems in the reply; do not change the student's text.

## Step 5: Write the data file and build

Write the notes as a JSON file, then build. For a long topic, write the data in sections (a few rows at a time) and assemble the file, rather than in one attempt.

```bash
python3 study_notes_build.py build  --data notes.json --out "Topic 4 Notes.docx"            # new document
python3 study_notes_build.py append --data notes.json --doc "My Notes.docx" --out "My Notes (updated).docx"
```

When appending, write to a new file and deliver that; overwrite the original only if the student asks. The script reuses the existing table's column widths and indent, and adds its own list numbering without disturbing the document's.

Data file format:

```json
{
  "title": "Topic 4: Market Failure",
  "label_set": "generic",
  "key_line": true,
  "page": "A4",
  "rows": [
    {"label": "Externalities", "depth": "deep", "items": [
      {"h": "Definition"},
      {"b": "**Externality** – a cost or benefit not reflected in the market price.", "tag": "KEY"},
      {"b": "Negative externalities lead to overproduction relative to the social optimum."},
      {"b": "e.g. factory pollution borne by nearby residents.", "sub": 1},
      {"b": "Positive externalities (e.g. vaccination) lead to underproduction."},
      {"h": "Correcting it"},
      {"l": "Identify the marginal external cost."},
      {"l": "Set a Pigouvian tax equal to it.", "tag": "METHOD"},
      {"eq": "MSC = MPC + MEC"},
      {"b": "*Coase (1960)*: bargaining fixes externalities if property rights are clear and transaction costs are low.", "star": true},
      {"b": "Fails when many parties are affected, because bargaining costs rise.", "sub": 1}
    ]},
    {"label": "Public goods", "items": [
      {"b": "**Public good** – non-excludable and non-rival, e.g. street lighting."}
    ]}
  ],
  "unsorted": [],
  "quick_recall": [
    {"label": "Externalities", "text": "Unpriced side effects; tax at the marginal external cost (Pigou) or bargain (Coase)."},
    {"label": "Public goods", "text": "Non-excludable and non-rival, so markets under-supply them."}
  ]
}
```

**Top-level fields**

| Field | Meaning |
|---|---|
| `title` | Topic heading |
| `label_set` | `"generic"` or `"law"` |
| `label_overrides` | Optional custom label text, e.g. `{"KEY": "CORE"}` |
| `key_line` | Show the one-line tag legend (default true) |
| `tagless` | Drop all tags and the key line |
| `new_page` | Start this topic on a new page |
| `page` | `"A4"` (default) or `"Letter"` for new documents. Use Letter for US or Canadian students or when asked |
| `rows` | The subtopic rows; a row may carry `"depth": "deep"` |
| `unsorted` | Items rendered in an "Unsorted" row (reformat mode) |
| `quick_recall` | One `{label, text}` per subtopic |
| `keep_whole_lines` | Rows estimated at or under this many lines are kept on one page (default 25). Lower it (for example to 12) if whole rows jump to the next page and leave gaps |

**Items in `items`**

| Item | Renders as |
|---|---|
| `{"h": "…"}` | Bold sub-heading |
| `{"b": "…"}` | Dash bullet. Optional flags: `tag`, `star`, `sub` (1 or 2 indent levels; never tagged), `dense` (long bullet on a hard idea, no length warning), `added` (grey ADDED marker), `verbatim` (the student's own long wording, no length warning) |
| `{"l": "…"}` | Lettered item; consecutive `l` items form one list |
| `{"eq": "…"}` | Centred equation line |
| `{"p": "…", "frame": "open"}` or `"close"` | Framing line: italic, no bullet, first or last item in a row (see "Framing lines") |
| `{"p": "…", "verbatim": true}` | The student's own unbulleted line, kept as written (reformat mode) |

**Inline markup:** `**bold**`, `*italic*`, `==highlight==`, `x^{2}`, `CF_{t}`. A backslash escapes a literal character (`\*`). Use × for multiplication, never a bare asterisk.

Read every WARNING the script prints and fix the data. Accept a warning only deliberately, with a one-line reason in the reply (for example "kept the eight demand types in one glossed bullet; each is explained"). The warnings cover:
- tagging: over-tagging, or more than one ★ in a row;
- structure: rows of five or more bullets with no sub-heading, topics with almost no sub-headings, several criteria in one bullet, arrow chains without a lettered list;
- lists and length: bare or mostly unexplained lists, long bullets not marked dense, thin deep rows;
- framing lines that are misplaced, too long, too many or repetitive;
- QUICK RECALL that is thin or missing;
- unclosed markup.

The first line of output is the script version.

## Step 6: Check length and appearance

**No page cap by default.** Length is an outcome of covering everything at the right depth. Measure it with `python3 study_notes_build.py pages --doc "<file>.docx"` and report it in the reply.

**If the student sets a cap** ("keep it to 3 pages"), measure with `pages --doc "<file>.docx" --cap N`. It prints the rendered page count, a content estimate and a verdict.

- **Several topics and one cap.** Unless the student says "each" or "per topic" (or answered that way), the cap is the total for everything in the request. Share it between topics by how much material and weight each has, not evenly. `pages` prints an estimate for each topic. State the reading in the reply ("2 pages read as the total for both topics").
- **A cap changes depth and row count, never structure.** Fit a cap by giving low-weight concepts less depth and trimming in the order below. Never fit it by turning sub-headings into inline labels, cramming several criteria or a lettered list into one bullet, stripping glosses, or merging different criteria into one row.
- **A cap is a ceiling, not a target.** Don't pad. If `pages` reports UNDER-FILLED (under about 80% of the cap), undo any squeezing before delivering: restore sub-headings, glosses, split rows and QUICK RECALL lines, and check nothing was skipped.
- **Check why it is over before trimming.** If the rendered count is over the cap but the content estimate is under it, a whole row has jumped to the next page and left a gap. Reorder rows, or lower `keep_whole_lines` (for example to 12), and rebuild instead of cutting content.
- **Leave a margin.** Word and LibreOffice wrap text slightly differently. Treat notes that only just fit as at risk, and trim lightly.

When content genuinely has to go, trim in this order, then rebuild and re-measure:

0. Framing lines.
1. Tool or admin rows (software how-to, reading lists, housekeeping).
2. Sub-bullets on low-weight concepts.
3. Worked-example detail, cut down to the inputs and the final answer.
4. Low-weight subtopics, cut to a one-line row (the row stays).
5. Thin rows on the same criterion, merged into their neighbours. Never merge different criteria into one row.
6. Explanatory sub-bullets on high-weight concepts, last.

Never cut tagged bullets, the ★, discrepancy flags, sub-headings, lettered lists, a recited list's QUICK RECALL line, or a subtopic's coverage entirely. QUICK RECALL lines may be shortened. If the cap still can't be met without dropping a subtopic, don't stop mid-run to ask: deliver the best fit, state the overage in the reply, and name the cut that would close it. (A tight cap should normally have been raised in the one round of questions.)

**Look at the pages.** If LibreOffice and a PDF-to-image tool are available, run `pages --keep-pdf out.pdf`, render the pages and look at them. Check that rows break sensibly, labels are coloured and equations show superscripts. If LibreOffice is missing, `pages` prints an estimate; say the count is approximate. Short rows are kept on one page; long rows are allowed to continue onto the next page so they don't leave large gaps.

**Reformat mode:** never trim the student's content without asking.

## Step 7: Deliver

Send the .docx. Keep the reply short:
- the profile line (one per topic if they differ);
- how a cap was read (total or per topic), and any defaults used because a question went unanswered;
- the topic added, its number of rows and its page count (against the cap, if one was set);
- any warnings accepted deliberately, each with its reason;
- one line on depth: which concepts got the fullest treatment (and which were kept brief), so the student can say "go deeper on X";
- the rows that got a framing line, if any, so the student can veto them;
- any discrepancies found in the sources;
- in reformat mode, the gaps note.

## Prioritise mode

When the student asks what matters most in a textbook, unit or set of materials (rather than for notes):

1. Build the concept map (Step 2b). Course materials (unit outline, tutorial sheets, past papers, slides) outweigh the textbook's own emphasis.
2. Reply with a ranked list, grouped as **Core**, **Important** and **Lighter**, with one line per topic on why it ranks there (for example "4 worked examples, in learning objectives, prerequisite for Ch 7").
3. Say what evidence was available and what was missing (for example "no past papers, so exam weight is inferred from the textbook and slides").
4. Offer to make notes next, using this map for depth.

No document is built unless the student asks for one.

## Reformat mode in detail

- **Keep the student's words.** Allowed changes are structural only: splitting text into rows, sub-headings and bullets; breaking a long sentence at a natural break into a bullet and a sub-bullet (connecting words like "and" or "which" may be dropped); bolding a lead term; capitalising the first letter of a bullet. Do not paraphrase, correct, or "improve". Mark long student bullets `"verbatim": true`.
- **Depth is theirs.** Do not expand or shorten their points to fit the depth table. Depth calibration applies only to content added in reformat + fill.
- **Labels and sub-headings:** use the student's own headings where they exist. Otherwise write short labels, which count as structure, not content.
- **Order:** keep the student's order unless grouping requires moving something, and mention any reordering.
- **Tags:** apply them only where the student's wording clearly fits a tag, under the same sparing rule. Their own bold or highlighting is a strong signal of what they consider key.
- **Framing lines:** never invent one. The student's own unbulleted lines are kept as `{"p": "…", "verbatim": true}` where they were.
- **Nothing dropped:** anything that does not fit a row goes in `unsorted`, which renders as an "Unsorted" row before QUICK RECALL.
- **QUICK RECALL** is written from the student's content in their own terms. Say in the reply that it was generated.
- **Nothing added** unless asked. After the document, give a short note listing possible gaps (slide topics missing from the notes, if slides were given), thin coverage of concepts that look high-weight, inconsistencies, figures that failed the verify step, and unclear points. The student decides what to do.
- **Reformat + fill:** add the missing content as new bullets with `"added": true`, which shows a grey ADDED marker, using depth calibration for the added material. Never edit the student's bullets.

## Format reference (fixed house style)

- Calibri throughout. Body 11pt; tag labels bold 10pt in their colours; ★ 11pt gold.
- Table 10774 dxa wide: left column 1702, right column 9072.
- New documents are A4 (or Letter) with 1 cm top and bottom margins and side margins sized to fit the table.
- Rows alternate white and F2F2F2 shading. QUICK RECALL spans both columns on FDF3D0.
- The title is centred, bold, with a yellow highlight. The key line sits centred beneath it at 10pt.
- Framing lines are italic 11pt with no bullet, first or last in a row.
- Short rows stay on one page; long rows may break across pages. Sub-headings stay with the line after them.
- The ★ line is highlighted yellow.
- When appending, the existing document's widths and label set are matched.

## Edge cases

- **A whole textbook uploaded for notes:** build the concept map, then make notes chapter by chapter (one topic per chapter, `new_page` for each), covering every chapter the student asked for. If they gave no scope, cover the chapters that match the slides or unit outline, and list the rest as available in the reply.
- **Several lectures in one request:** one topic per lecture unless the student wants them merged. Run one build or append per topic, each starting on a new page (see Step 1).
- **Diagram-heavy slides:** describe the diagrams in words in the bullets ("Figure: supply shifts left…"). The document has no images.
- **Scanned PDFs:** render the pages to images and read them.
- **Non-English material:** write the notes in the language of the material.
- **Existing document not in this format** (no two-column table): do not append. Offer a new document, or to reformat the old notes with reformat mode.
- **Older sections without tags or shading:** append in the matching label set, and mention that the older sections can be reformatted if the student wants consistency.
- **Another output format requested** (PDF, for example): build the .docx first, then convert it if a converter such as LibreOffice is available.

## The build script

Save everything in this block as `study_notes_build.py`.

```python
#!/usr/bin/env python3
"""study_notes_build.py: build or append two-column study notes (.docx). Python 3 stdlib only.

Commands
  build   --data notes.json --out notes.docx [--page A4|Letter]
  append  --data notes.json --doc existing.docx --out updated.docx
  inspect --doc existing.docx      report format, labels, topics already in a notes document
  extract --doc file.docx          dump text with **bold**, *italic*, ==highlight== kept (for reformat mode)
  pages   --doc notes.docx [--cap N] [--keep-pdf out.pdf]
                                   rendered page count (LibreOffice) plus a content estimate, per topic when
                                   there are several; with --cap, says whether the notes are within, near,
                                   over or well under the cap and why (a cap is read as the total)

Rows may carry "depth": "deep" (warns if the row is too thin). Bullets may carry "dense": true
(a long bullet on a hard idea, no length warning) and "sub": 1 or 2 (indent level).
Framing lines: {"p": "...", "frame": "open"} first in a row, or {"p": "...", "frame": "close"} last.
They render in italics with no bullet and are checked for position, length, count and repetition.
{"p": "...", "verbatim": true} keeps a student's own unbulleted line (reformat mode).

Inline markup inside any text field
  **bold**   *italic*   ==highlight==   x^{2}  (superscript)   CF_{t}  (subscript)
  A backslash escapes the next character: \\*  \\=  \\^  \\_
"""
import argparse, json, math, os, re, shutil, subprocess, sys, tempfile, zipfile
import xml.etree.ElementTree as ET

W = 'http://schemas.openxmlformats.org/wordprocessingml/2006/main'
R = 'http://schemas.openxmlformats.org/officeDocument/2006/relationships'
FONT = 'Calibri'
BODY_SZ = 22          # 11pt
TAG_SZ = 20           # 10pt
COLORS = {'KEY': '1F4E79', 'METHOD': '6A3D9A', 'EVIDENCE': 'B45309', 'APPLY': '2F6F4E'}
STAR_COLOR = 'B8860B'
ADDED_COLOR = '7F7F7F'
ROW_SHADE = 'F2F2F2'
RECALL_SHADE = 'FDF3D0'
LEFT_W, RIGHT_W = 1702, 9072
LABEL_SETS = {
    'generic': {'KEY': 'KEY', 'METHOD': 'METHOD', 'EVIDENCE': 'EVIDENCE', 'APPLY': 'APPLY'},
    'law': {'KEY': 'RULE', 'METHOD': 'TEST', 'EVIDENCE': 'CASE', 'APPLY': 'POLICY'},
}
MEANINGS = {
    'generic': {'KEY': 'must know', 'METHOD': 'how to apply', 'EVIDENCE': 'leading example or source', 'APPLY': 'practical point'},
    'law': {'KEY': 'rule to state', 'METHOD': 'test to apply', 'EVIDENCE': 'leading case', 'APPLY': 'policy point'},
}
TAG_ALIASES = {'KEY': 'KEY', 'RULE': 'KEY', 'METHOD': 'METHOD', 'TEST': 'METHOD',
               'EVIDENCE': 'EVIDENCE', 'CASE': 'EVIDENCE', 'APPLY': 'APPLY', 'POLICY': 'APPLY'}
VERSION = '2.2'
PAGES = {'A4': (11906, 16838), 'LETTER': (12240, 15840)}
WARNINGS = []
FRAMED = []           # labels of rows that carry a framing line
FRAME_MAX_WORDS = 25
STOCK_OPENINGS = ('in summary', 'overall', 'key takeaway', 'to summarise', 'to summarize', 'in short',
                  'in conclusion', 'in essence', 'this row', 'this section', 'this topic')
STOPWORDS = set('a an the and or of to in on for with by is are be as at from that this it its which their '
                'they than not but so into can each'.split())


def warn(msg):
    if msg not in WARNINGS:
        WARNINGS.append(msg)


# ---------------------------------------------------------------- runs and inline markup
def esc(t):
    return t.replace('&', '&amp;').replace('<', '&lt;').replace('>', '&gt;').replace('"', '&quot;')


def run(text, b=False, i=False, hl=False, vert=None, color=None, sz=BODY_SZ):
    if text == '':
        return ''
    p = [f'<w:rFonts w:ascii="{FONT}" w:hAnsi="{FONT}" w:cs="{FONT}"/>']
    if b:
        p.append('<w:b/><w:bCs/>')
    if i:
        p.append('<w:i/><w:iCs/>')
    if color:
        p.append(f'<w:color w:val="{color}"/>')
    p.append(f'<w:sz w:val="{sz}"/><w:szCs w:val="{sz}"/>')
    if hl:
        p.append('<w:highlight w:val="yellow"/>')
    if vert:
        p.append(f'<w:vertAlign w:val="{vert}"/>')
    return f'<w:r><w:rPr>{"".join(p)}</w:rPr><w:t xml:space="preserve">{esc(text)}</w:t></w:r>'


def parse_inline(s):
    """Return a list of (text, bold, italic, highlight, vert) segments."""
    out, buf = [], []
    b = i = hl = False
    k = 0

    def flush():
        if buf:
            out.append((''.join(buf), b, i, hl, None))
            buf.clear()

    while k < len(s):
        c = s[k]
        if c == '\\' and k + 1 < len(s):
            buf.append(s[k + 1]); k += 2; continue
        if s.startswith('**', k):
            flush(); b = not b; k += 2; continue
        if s.startswith('==', k):
            flush(); hl = not hl; k += 2; continue
        if c == '*':
            flush(); i = not i; k += 1; continue
        if c in '^_' and k + 1 < len(s) and s[k + 1] == '{':
            end = s.find('}', k + 2)
            if end != -1:
                flush()
                out.append((s[k + 2:end], b, i, hl, 'superscript' if c == '^' else 'subscript'))
                k = end + 1; continue
        buf.append(c); k += 1
    flush()
    if b or i or hl:
        warn(f'Unclosed ** / * / == markup in: {s[:60]}')
    return out


def runs_from(s, force_hl=False, color=None, force_i=False):
    return ''.join(run(t, b, i or force_i, hl or force_hl, v, color) for t, b, i, hl, v in parse_inline(s))


def plain_text(s):
    return ''.join(t for t, *_ in parse_inline(s))


REF_PAREN = re.compile(r'\((?:Table|Tables|Fig|Figure|CPC|s |ss |p |pp |Ch |e\.g\.|see |[\d+ ,.\-–]+\))', re.I)


def list_items(flat):
    """Split a bullet into comma/semicolon-separated items, ignoring separators inside brackets."""
    body = flat.split(':', 1)[1] if re.match(r'^[^,;]{1,40}:', flat) else flat
    items, depth, cur = [], 0, ''
    for ch in body:
        if ch == '(':
            depth += 1
        elif ch == ')':
            depth = max(0, depth - 1)
        if ch in ',;' and depth == 0:
            items.append(cur.strip()); cur = ''
        else:
            cur += ch
    if cur.strip():
        items.append(cur.strip())
    return [i for i in items if i]


def is_glossed(item):
    """True if a list item carries an explanation: a bracketed gloss that is not just a reference, or a dash."""
    return bool(re.search(r'\(', item) and not REF_PAREN.search(item)) or ' – ' in item or ' = ' in item


# ---------------------------------------------------------------- paragraphs
def para(runs_xml, num_id=None, ind=None, keep_next=False, jc=None):
    ppr = []
    if keep_next:
        ppr.append('<w:keepNext/>')
    if num_id is not None:
        ppr.append(f'<w:numPr><w:ilvl w:val="0"/><w:numId w:val="{num_id}"/></w:numPr>')
    ppr.append('<w:spacing w:before="0" w:after="0" w:line="240" w:lineRule="auto"/>')
    if ind:
        ppr.append(f'<w:ind w:left="{ind[0]}" w:hanging="{ind[1]}"/>')
    if jc:
        ppr.append(f'<w:jc w:val="{jc}"/>')
    ppr.append(f'<w:rPr><w:rFonts w:ascii="{FONT}" w:hAnsi="{FONT}" w:cs="{FONT}"/>'
               f'<w:sz w:val="{BODY_SZ}"/><w:szCs w:val="{BODY_SZ}"/></w:rPr>')
    return f'<w:p><w:pPr>{"".join(ppr)}</w:pPr>{runs_xml}</w:p>'


class Numbering:
    """Allocates numbering ids: one dash-bullet list, and a fresh lettered list per group."""

    def __init__(self, abs_base=1, num_base=1):
        self.abs_dash, self.abs_letter = abs_base, abs_base + 1
        self.dash = num_base
        self.next_num = num_base + 1
        self.letter_nums = []

    def new_letter_group(self):
        n = self.next_num
        self.next_num += 1
        self.letter_nums.append(n)
        return n

    def abstract_xml(self):
        rpr = f'<w:rPr><w:rFonts w:ascii="{FONT}" w:hAnsi="{FONT}" w:cs="{FONT}" w:hint="default"/></w:rPr>'
        dash = (f'<w:abstractNum w:abstractNumId="{self.abs_dash}"><w:multiLevelType w:val="singleLevel"/>'
                f'<w:lvl w:ilvl="0"><w:start w:val="1"/><w:numFmt w:val="bullet"/><w:lvlText w:val="–"/>'
                f'<w:lvlJc w:val="left"/><w:pPr><w:ind w:left="360" w:hanging="260"/></w:pPr>{rpr}</w:lvl></w:abstractNum>')
        letter = (f'<w:abstractNum w:abstractNumId="{self.abs_letter}"><w:multiLevelType w:val="singleLevel"/>'
                  f'<w:lvl w:ilvl="0"><w:start w:val="1"/><w:numFmt w:val="lowerLetter"/><w:lvlText w:val="(%1)"/>'
                  f'<w:lvlJc w:val="left"/><w:pPr><w:ind w:left="400" w:hanging="320"/></w:pPr>{rpr}</w:lvl></w:abstractNum>')
        return dash + letter

    def num_xml(self):
        x = f'<w:num w:numId="{self.dash}"><w:abstractNumId w:val="{self.abs_dash}"/></w:num>'
        for n in self.letter_nums:
            x += (f'<w:num w:numId="{n}"><w:abstractNumId w:val="{self.abs_letter}"/>'
                  f'<w:lvlOverride w:ilvl="0"><w:startOverride w:val="1"/></w:lvlOverride></w:num>')
        return x


# ---------------------------------------------------------------- content
def norm_tag(tag, where):
    if not tag:
        return None
    t = TAG_ALIASES.get(str(tag).upper())
    if not t:
        warn(f'Unknown tag "{tag}" in {where}; rendered without a tag')
    return t


def tag_runs(tag, labels):
    return run(labels[tag] + ' ', b=True, color=COLORS[tag], sz=TAG_SZ)


def bullet_xml(item, labels, nb, where, letter_num=None):
    text = item.get('b', item.get('l', ''))
    sub = item.get('sub', False)
    if sub is True:
        sub = 1
    star = item.get('star', False)
    tag = norm_tag(item.get('tag'), where)
    if star and tag not in (None, 'EVIDENCE'):
        warn(f'star used with tag {tag} in {where}; star implies EVIDENCE, tag changed')
    if star:
        tag = 'EVIDENCE'
    if sub and (tag or star):
        warn(f'sub-bullet in {where} had a tag or star; sub-bullets are always plain')
        tag, star = None, False
    prefix = ''
    if item.get('added'):
        prefix += run('ADDED ', b=True, color=ADDED_COLOR, sz=TAG_SZ)
    if star:
        prefix += run('★ ', b=True, color=STAR_COLOR, sz=BODY_SZ)
    if tag:
        prefix += tag_runs(tag, labels)
    flat = plain_text(text)
    words = len(flat.split())
    if words > 28 and not (item.get('verbatim') or item.get('dense')):
        warn(f'Long bullet ({words} words) in {where}: "{flat[:50]}..."')
    if not item.get('verbatim') and 'e.g.' not in flat:          # an e.g. list is illustrative, not a list to recite
        parts = list_items(flat)
        glossed = sum(1 for p in parts if is_glossed(p))
        bare = [p for p in parts if not is_glossed(p)]
        short_terms = bare and sum(len(p.split()) for p in bare) / len(bare) < 2.5
        if len(parts) >= 10 and glossed == 0 and ' – ' not in flat:
            warn(f'Bare list of about {len(parts)} items in {where}: gloss the items that matter or split it under a sub-heading')
        elif len(parts) >= 6 and glossed < len(parts) / 2 and short_terms:
            warn(f'List of mostly unexplained terms ({glossed} of {len(parts)} glossed) in {where}: "{flat[:40]}...". '
                 f'Gloss the terms a student must understand, or split the list')
        labels_inline = len(re.findall(r'(?:^|[.;]\s+)[A-Z][A-Za-z ,/-]{1,28}:\s', flat))
        bold_runs = len(re.findall(r'\*\*[^*]+\*\*', text))
        if labels_inline >= 3 or bold_runs >= 3:
            warn(f'Several criteria crammed into one bullet in {where}: "{flat[:40]}...". '
                 f'Give each criterion its own bullet, or its own sub-heading if it needs more than one')
    body = runs_from(text, force_hl=star)
    if letter_num is not None:
        return para(prefix + body, num_id=letter_num), tag, star
    ind = (360 + 360 * min(int(sub), 2), 260) if sub else None
    return para(prefix + body, num_id=nb.dash, ind=ind), tag, star


def cell(width, paras_xml, shade=None, span=None):
    tcpr = f'<w:tcW w:w="{width}" w:type="dxa"/>'
    if span:
        tcpr += f'<w:gridSpan w:val="{span}"/>'
    if shade:
        tcpr += f'<w:shd w:val="clear" w:color="auto" w:fill="{shade}"/>'
    if not paras_xml:
        paras_xml = para('')
    return f'<w:tc><w:tcPr>{tcpr}</w:tcPr>{paras_xml}</w:tc>'


def right_cell_paras(items, labels, nb, where, depth=None):
    out = []
    tagged = plain = stars = 0
    letter_num = None
    for idx, item in enumerate(items):
        if not isinstance(item, dict):
            item = {'b': str(item)}
        if 'l' in item:
            if letter_num is None:
                letter_num = nb.new_letter_group()
            x, tag, star = bullet_xml(item, labels, nb, where, letter_num)
            out.append(x)
            tagged += bool(tag); plain += not tag; stars += star
            continue
        letter_num = None
        if 'h' in item:
            if out:
                out.append(para(''))
            out.append(para(''.join(run(t, True, i, hl, v) for t, b, i, hl, v in parse_inline(item['h'])),
                            keep_next=True))
        elif 'b' in item:
            x, tag, star = bullet_xml(item, labels, nb, where)
            out.append(x)
            if not item.get('sub'):
                tagged += bool(tag); plain += not tag
            stars += star
        elif 'eq' in item:
            out.append(para(runs_from(item['eq']), jc='center'))
        elif 'p' in item:
            frame = item.get('frame')
            if item.get('tag') or item.get('star'):
                warn(f'{where}: tag or star on a plain line is ignored; if it must be tagged, make it a bullet')
            if frame in ('open', 'close'):
                out.append(para(runs_from(item['p'], force_i=True), keep_next=(frame == 'open')))
            else:
                if frame:
                    warn(f'{where}: frame "{frame}" not recognised; use "open" or "close"')
                elif not item.get('verbatim'):
                    warn(f'{where}: plain line with no "frame" or "verbatim"; use a bullet, a sub-heading or a framing line')
                out.append(para(runs_from(item['p'])))
        else:
            warn(f'Unrecognised item in {where}: {json.dumps(item)[:60]}')
    # framing and plain lines are not content, so they never rescue a thin deep row
    content_lines = sum(1 for it in items if isinstance(it, dict) and ('b' in it or 'l' in it or 'eq' in it))
    if depth == 'deep' and content_lines < 4:
        warn(f'{where} is marked deep but has only {content_lines} content lines; add the why, conditions, steps or common error')
    if stars > 1:
        warn(f'{where} has {stars} starred items; keep one star per subtopic')
    if tagged >= 2 and tagged > plain:
        warn(f'{where} looks over-tagged ({tagged} tagged vs {plain} plain); aim for about 1 tagged per 2 to 3 plain, '
             f'and at most one tag in a row of three or fewer bullets')
    dicts = [it for it in items if isinstance(it, dict)]
    has_h = any('h' in it for it in dicts)
    has_l = any('l' in it for it in dicts)
    top_b = [it for it in dicts if 'b' in it and not it.get('sub')]
    if len(top_b) >= 5 and not has_h:
        warn(f'{where} has {len(top_b)} bullets and no sub-heading; group them under sub-headings')
    if not has_l and any(plain_text(it['b']).count('→') >= 3 for it in dicts if 'b' in it):
        warn(f'{where} has a sequence of four or more steps written as an arrow chain; use a lettered list')
    return ''.join(out)


def word_set(s):
    return {w for w in re.findall(r"[a-z0-9']+", plain_text(s).lower()) if w not in STOPWORDS}


def check_frames(row, label, recall_texts):
    """Warn on framing lines that break the rules. Returns True if the row has any."""
    items = [it if isinstance(it, dict) else {'b': str(it)} for it in row.get('items', [])]
    where = f'row "{label}"'
    frames = [(i, it) for i, it in enumerate(items) if 'p' in it and it.get('frame') in ('open', 'close')]
    if not frames:
        return False
    top = [it for it in items if ('b' in it and not it.get('sub')) or 'l' in it]
    kinds = [it['frame'] for _, it in frames]
    first_slot = 1 if items and 'h' in items[0] else 0
    for i, it in frames:
        txt = plain_text(it['p'])
        n_words = len(txt.split())
        if n_words > FRAME_MAX_WORDS:
            warn(f'{where}: framing line is {n_words} words; keep it to one sentence of {FRAME_MAX_WORDS} words or fewer')
        stripped = re.sub(r'\b(e\.g|i\.e|etc|cf|vs|no|Fig|Table|Ch|ss?)\.', '', txt)
        if len(re.findall(r'[.!?](?=\s|$)', stripped)) > 1:
            warn(f'{where}: framing line has more than one sentence')
        if txt.lower().lstrip().startswith(STOCK_OPENINGS):
            warn(f'{where}: framing line opens with a stock phrase ("{txt[:20]}..."); say the specific point instead')
        if it['frame'] == 'open' and i not in (0, first_slot):
            warn(f'{where}: opening framing line is mid-row; it must be the first item (or first after a sub-heading)')
        if it['frame'] == 'close' and i != len(items) - 1:
            warn(f'{where}: closing framing line is mid-row; it must be the last item')
        ws = word_set(txt)
        for ref in [label] + list(recall_texts):
            rs = word_set(ref)
            if ws and rs and len(ws & rs) / len(ws) >= 0.6:
                warn(f'{where}: framing line largely repeats the row label or a QUICK RECALL line; cut it')
                break
    if kinds.count('open') > 1 or kinds.count('close') > 1:
        warn(f'{where}: more than one opening or closing framing line')
    if 'open' in kinds and 'close' in kinds and row.get('depth') != 'deep':
        warn(f'{where}: both opening and closing framing lines in a row not marked deep; keep one')
    if len(top) <= 3:
        warn(f'{where}: framing line in a row with {len(top)} bullets; rows of three or fewer bullets get none')
    if 'open' in kinds:
        first_b = next((it for it in items if 'b' in it and not it.get('sub')), None)
        if first_b and TAG_ALIASES.get(str(first_b.get('tag') or '').upper()) == 'KEY':
            warn(f'{where}: opening framing line before a KEY first bullet; the KEY line already orients the row')
    return True


def table_xml(data, labels, nb, left_w, right_w, tbl_ind=0):
    total = left_w + right_w
    rows = []
    content_rows = list(data.get('rows', []))
    if data.get('unsorted'):
        content_rows.append({'label': 'Unsorted', 'items': data['unsorted']})
    recall_texts = [r.get('text', '') for r in (data.get('quick_recall') or [])]
    keep_whole = int(data.get('keep_whole_lines', 25))
    for n, row in enumerate(content_rows):
        shade = ROW_SHADE if n % 2 == 1 else None
        label = row.get('label') or row.get('subtopic') or ''
        where = f'row "{label}"'
        if check_frames(row, label, recall_texts):
            FRAMED.append(label)
        left = para(''.join(run(t, True, i, hl, v) for t, b, i, hl, v in parse_inline(label)))
        right = right_cell_paras(row.get('items', []), labels, nb, where, row.get('depth'))
        cpl = max(20, (right_w - 600) // 100)
        its = row.get('items', [])
        est = sum(max(1, math.ceil(len(plain_text(str(next(iter(it.values()))) if isinstance(it, dict) else str(it))) / cpl))
                  for it in its)
        est += max(0, sum(1 for it in its if isinstance(it, dict) and 'h' in it) - 1)   # blank line before each later sub-heading
        trpr = '<w:trPr><w:cantSplit/></w:trPr>' if est <= keep_whole else ''
        rows.append(f'<w:tr>{trpr}{cell(left_w, left, shade)}{cell(right_w, right, shade)}</w:tr>')
    real_rows = len(data.get('rows', []))
    if real_rows and len(FRAMED) > math.ceil(real_rows / 3):
        warn(f'{len(FRAMED)} of {real_rows} rows have framing lines; the ceiling is about one row in four '
             f'(warning above one in three). Keep only the rows that fail the deletion test')
    rows_with_h = sum(1 for r in data.get('rows', []) if any(isinstance(it, dict) and 'h' in it for it in r.get('items', [])))
    if real_rows >= 6 and rows_with_h < real_rows / 5:
        warn(f'Only {rows_with_h} of {real_rows} rows use sub-headings. Check each row: more than one angle or '
             f'criterion, or a criterion that needs two or more bullets, means sub-headings')
    n_recall = len(data.get('quick_recall') or [])
    if real_rows and data.get('quick_recall') and n_recall < math.ceil(0.75 * real_rows):
        warn(f'QUICK RECALL has {n_recall} lines for {real_rows} rows; every list the student must recite needs its own line')
    recall = data.get('quick_recall')
    if recall:
        ps = [para(run('QUICK RECALL', b=True), keep_next=True)]
        for r in recall:
            lab = r.get('label') or r.get('subtopic')
            txt = (f'{lab}: ' if lab else '') + r['text']
            ps.append(para(runs_from(txt), num_id=nb.dash))
        rows.append(f'<w:tr><w:trPr><w:cantSplit/></w:trPr>{cell(total, "".join(ps), RECALL_SHADE, span=2)}</w:tr>')
    elif content_rows:
        warn('No quick_recall given; every topic should end with a QUICK RECALL row')
    borders = ''.join(f'<w:{e} w:val="single" w:sz="4" w:space="0" w:color="auto"/>'
                      for e in ('top', 'left', 'bottom', 'right', 'insideH', 'insideV'))
    return (f'<w:tbl><w:tblPr><w:tblW w:w="{total}" w:type="dxa"/><w:tblInd w:w="{tbl_ind}" w:type="dxa"/>'
            f'<w:tblBorders>{borders}</w:tblBorders><w:tblLayout w:type="fixed"/>'
            f'<w:tblCellMar><w:left w:w="108" w:type="dxa"/><w:right w:w="108" w:type="dxa"/></w:tblCellMar>'
            f'<w:tblLook w:val="04A0" w:firstRow="0" w:lastRow="0" w:firstColumn="0" w:lastColumn="0" w:noHBand="0" w:noVBand="1"/>'
            f'</w:tblPr><w:tblGrid><w:gridCol w:w="{left_w}"/><w:gridCol w:w="{right_w}"/></w:tblGrid>'
            f'{"".join(rows)}</w:tbl>')


def key_line_xml(label_set, labels):
    m = MEANINGS['law' if label_set == 'law' else 'generic']
    parts = [run('Key: ', b=True, sz=TAG_SZ)]
    order = ['KEY', 'METHOD', 'EVIDENCE', 'APPLY']
    for n, t in enumerate(order):
        if t == 'EVIDENCE':
            parts.append(run('★ ', b=True, color=STAR_COLOR, sz=TAG_SZ))
        parts.append(run(labels[t] + ' ', b=True, color=COLORS[t], sz=TAG_SZ))
        parts.append(run(m[t] + ('   ' if n < 3 else ''), sz=TAG_SZ))
    return para(''.join(parts), jc='center')


def topic_xml(data, nb, left_w, right_w, tbl_ind=0):
    label_set = data.get('label_set', 'generic')
    if label_set not in LABEL_SETS:
        warn(f'label_set "{label_set}" unknown; using generic')
        label_set = 'generic'
    labels = dict(LABEL_SETS[label_set])
    for k, v in (data.get('label_overrides') or {}).items():
        k2 = TAG_ALIASES.get(k.upper())
        if k2:
            labels[k2] = v
    title = para(''.join(run(t, True, i, True, v) for t, b, i, hl, v in parse_inline(data.get('title', 'Notes'))),
                 jc='center', keep_next=True)
    if data.get('new_page'):
        title = title.replace('<w:pPr><w:keepNext/>', '<w:pPr><w:keepNext/><w:pageBreakBefore/>', 1)
    parts = [title]
    if data.get('key_line', True) and not data.get('tagless'):
        parts.append(key_line_xml(label_set, labels))
    if data.get('tagless'):
        for row in data.get('rows', []):
            for it in row.get('items', []):
                if isinstance(it, dict):
                    it.pop('tag', None); it.pop('star', None)
    parts.append(para(''))
    parts.append(table_xml(data, labels, nb, left_w, right_w, tbl_ind))
    parts.append(para(''))
    return ''.join(parts)


# ---------------------------------------------------------------- package parts
NS_DECL = (f'xmlns:w="{W}" xmlns:r="{R}"')


def styles_xml():
    return (f'<?xml version="1.0" encoding="UTF-8" standalone="yes"?><w:styles {NS_DECL}>'
            f'<w:docDefaults><w:rPrDefault><w:rPr><w:rFonts w:ascii="{FONT}" w:eastAsia="{FONT}" w:hAnsi="{FONT}" w:cs="{FONT}"/>'
            f'<w:sz w:val="{BODY_SZ}"/><w:szCs w:val="{BODY_SZ}"/><w:lang w:val="en-AU"/></w:rPr></w:rPrDefault>'
            f'<w:pPrDefault><w:pPr><w:spacing w:after="0" w:line="240" w:lineRule="auto"/></w:pPr></w:pPrDefault></w:docDefaults>'
            f'<w:style w:type="paragraph" w:default="1" w:styleId="Normal"><w:name w:val="Normal"/><w:qFormat/></w:style>'
            f'<w:style w:type="table" w:default="1" w:styleId="TableNormal"><w:name w:val="Normal Table"/><w:uiPriority w:val="99"/>'
            f'<w:semiHidden/><w:unhideWhenUsed/><w:tblPr><w:tblInd w:w="0" w:type="dxa"/><w:tblCellMar>'
            f'<w:top w:w="0" w:type="dxa"/><w:left w:w="108" w:type="dxa"/><w:bottom w:w="0" w:type="dxa"/>'
            f'<w:right w:w="108" w:type="dxa"/></w:tblCellMar></w:tblPr></w:style></w:styles>')


def numbering_part(nb):
    return (f'<?xml version="1.0" encoding="UTF-8" standalone="yes"?><w:numbering {NS_DECL}>'
            f'{nb.abstract_xml()}{nb.num_xml()}</w:numbering>')


SETTINGS = (f'<?xml version="1.0" encoding="UTF-8" standalone="yes"?><w:settings {NS_DECL}>'
            '<w:defaultTabStop w:val="720"/><w:compat><w:compatSetting w:name="compatibilityMode" '
            'w:uri="http://schemas.microsoft.com/office/word" w:val="15"/></w:compat></w:settings>')
CONTENT_TYPES = ('<?xml version="1.0" encoding="UTF-8" standalone="yes"?>'
                 '<Types xmlns="http://schemas.openxmlformats.org/package/2006/content-types">'
                 '<Default Extension="rels" ContentType="application/vnd.openxmlformats-package.relationships+xml"/>'
                 '<Default Extension="xml" ContentType="application/xml"/>'
                 '<Override PartName="/word/document.xml" ContentType="application/vnd.openxmlformats-officedocument.wordprocessingml.document.main+xml"/>'
                 '<Override PartName="/word/styles.xml" ContentType="application/vnd.openxmlformats-officedocument.wordprocessingml.styles+xml"/>'
                 '<Override PartName="/word/numbering.xml" ContentType="application/vnd.openxmlformats-officedocument.wordprocessingml.numbering+xml"/>'
                 '<Override PartName="/word/settings.xml" ContentType="application/vnd.openxmlformats-officedocument.wordprocessingml.settings+xml"/>'
                 '</Types>')
ROOT_RELS = ('<?xml version="1.0" encoding="UTF-8" standalone="yes"?>'
             '<Relationships xmlns="http://schemas.openxmlformats.org/package/2006/relationships">'
             '<Relationship Id="rId1" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument" Target="word/document.xml"/>'
             '</Relationships>')
DOC_RELS = ('<?xml version="1.0" encoding="UTF-8" standalone="yes"?>'
            '<Relationships xmlns="http://schemas.openxmlformats.org/package/2006/relationships">'
            '<Relationship Id="rId1" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles" Target="styles.xml"/>'
            '<Relationship Id="rId2" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/numbering" Target="numbering.xml"/>'
            '<Relationship Id="rId3" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/settings" Target="settings.xml"/>'
            '</Relationships>')


def write_zip(out, parts):
    tmp = out + '.tmp'
    with zipfile.ZipFile(tmp, 'w', zipfile.ZIP_DEFLATED) as z:
        order = ['[Content_Types].xml'] + [k for k in parts if k != '[Content_Types].xml']
        for name in order:
            data = parts[name]
            z.writestr(name, data.encode('utf-8') if isinstance(data, str) else data)
    os.replace(tmp, out)


def check_xml(name, text):
    try:
        ET.fromstring(text.encode('utf-8'))
    except ET.ParseError as e:
        sys.exit(f'ERROR: generated {name} is not well-formed XML: {e}')


def load_data(path):
    with open(path, encoding='utf-8') as f:
        d = json.load(f)
    if not d.get('rows') and not d.get('unsorted'):
        sys.exit('ERROR: data file has no "rows"')
    return d


def report():
    print(f'study-notes build v{VERSION}')
    for w in WARNINGS:
        print('WARNING: ' + w)
    if WARNINGS:
        print(f'{len(WARNINGS)} warning(s): fix each one, or accept it deliberately and say why in the reply')
    if FRAMED:
        print(f'FRAMING LINES in {len(FRAMED)} row(s): ' + '; '.join(FRAMED) + ' (name these in the reply)')
    else:
        print('FRAMING LINES: none')


# ---------------------------------------------------------------- commands
def cmd_build(a):
    data = load_data(a.data)
    page = (a.page or data.get('page') or 'A4').upper()
    pw, ph = PAGES.get(page, PAGES['A4'])
    side = max(360, (pw - (LEFT_W + RIGHT_W)) // 2)
    nb = Numbering()
    body = topic_xml(data, nb, LEFT_W, RIGHT_W, 0)
    sect = (f'<w:sectPr><w:pgSz w:w="{pw}" w:h="{ph}"/><w:pgMar w:top="567" w:right="{side}" w:bottom="567" '
            f'w:left="{side}" w:header="284" w:footer="284" w:gutter="0"/></w:sectPr>')
    doc = (f'<?xml version="1.0" encoding="UTF-8" standalone="yes"?><w:document {NS_DECL}>'
           f'<w:body>{body}{sect}</w:body></w:document>')
    parts = {'[Content_Types].xml': CONTENT_TYPES, '_rels/.rels': ROOT_RELS,
             'word/_rels/document.xml.rels': DOC_RELS, 'word/document.xml': doc,
             'word/styles.xml': styles_xml(), 'word/numbering.xml': numbering_part(nb),
             'word/settings.xml': SETTINGS}
    for k, v in parts.items():
        check_xml(k, v)
    write_zip(a.out, parts)
    report()
    print(f'OK: built {a.out} ({len(data.get("rows", []))} rows, labels: {data.get("label_set", "generic")})')


def read_zip(path):
    with zipfile.ZipFile(path) as z:
        return {n: z.read(n) for n in z.namelist() if not n.endswith('/')}


def existing_geometry(doc_xml):
    """Reuse the widths of an existing two-column notes table, else fit to the page's text width."""
    root = ET.fromstring(doc_xml)
    q = lambda t: f'{{{W}}}{t}'
    for tbl in root.iter(q('tbl')):
        cols = [int(g.get(q('w'))) for g in tbl.iter(q('gridCol')) if g.get(q('w'))]
        if len(cols) == 2:
            ind = tbl.find(f'{q("tblPr")}/{q("tblInd")}')
            return cols[0], cols[1], int(ind.get(q('w'))) if ind is not None and ind.get(q('w')) else 0
    sect = list(root.iter(q('sectPr')))
    width = LEFT_W + RIGHT_W
    if sect:
        s = sect[-1]
        pg, mar = s.find(q('pgSz')), s.find(q('pgMar'))
        if pg is not None and mar is not None:
            width = int(pg.get(q('w'))) - int(mar.get(q('left'), 1440)) - int(mar.get(q('right'), 1440))
    left = round(width * LEFT_W / (LEFT_W + RIGHT_W))
    return left, width - left, 0


def cmd_append(a):
    data = load_data(a.data)
    parts = read_zip(a.doc)
    doc = parts['word/document.xml'].decode('utf-8')
    if f'xmlns:w="{W}"' not in doc[:3000]:
        sys.exit('ERROR: document does not use the standard w: namespace prefix; cannot append safely')
    left_w, right_w, ind = existing_geometry(parts['word/document.xml'])
    if data.get('match_widths') is False:
        left_w, right_w, ind = LEFT_W, RIGHT_W, ind
    num = parts.get('word/numbering.xml', b'').decode('utf-8')
    if num:
        abs_ids = [int(x) for x in re.findall(r'<w:abstractNum\b[^>]*w:abstractNumId="(\d+)"', num)]
        num_ids = [int(x) for x in re.findall(r'<w:num\b[^>]*w:numId="(\d+)"', num)]
        nb = Numbering(max(abs_ids + [0]) + 1, max(num_ids + [0]) + 1)
    else:
        nb = Numbering()
    body = topic_xml(data, nb, left_w, right_w, ind)
    pos = doc.rfind('<w:sectPr')
    if pos == -1:
        pos = doc.rfind('</w:body>')
    doc = doc[:pos] + body + doc[pos:]
    if num:
        m = re.search(r'<w:num\s', num)
        cut = m.start() if m else num.rfind('</w:numbering>')
        num = num[:cut] + nb.abstract_xml() + num[cut:]
        e = num.rfind('</w:numbering>')
        num = num[:e] + nb.num_xml() + num[e:]
    else:
        num = numbering_part(nb)
        rels = parts['word/_rels/document.xml.rels'].decode('utf-8')
        if 'relationships/numbering"' not in rels:
            rels = rels.replace('</Relationships>',
                                '<Relationship Id="rIdStudyNotesNum" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/numbering" Target="numbering.xml"/></Relationships>')
            parts['word/_rels/document.xml.rels'] = rels
        ct = parts['[Content_Types].xml'].decode('utf-8')
        if '/word/numbering.xml' not in ct:
            ct = ct.replace('</Types>', '<Override PartName="/word/numbering.xml" ContentType="application/vnd.openxmlformats-officedocument.wordprocessingml.numbering+xml"/></Types>')
            parts['[Content_Types].xml'] = ct
    check_xml('document.xml', doc)
    check_xml('numbering.xml', num)
    parts['word/document.xml'] = doc
    parts['word/numbering.xml'] = num
    write_zip(a.out, parts)
    report()
    print(f'OK: appended "{plain_text(data.get("title", ""))}" to {a.out} (columns {left_w}/{right_w})')


def iter_body_paras(root):
    """Yield (paragraph element, in_table) in document order."""
    q = lambda t: f'{{{W}}}{t}'
    body = root.find(q('body'))

    def walk(el, in_tbl):
        for ch in el:
            if ch.tag == q('p'):
                yield ch, in_tbl
            elif ch.tag in (q('tbl'), q('tr'), q('tc'), q('sdt'), q('sdtContent')):
                yield from walk(ch, in_tbl or ch.tag == q('tbl'))
    yield from walk(body, False)


def para_markup(p):
    q = lambda t: f'{{{W}}}{t}'
    segs = []
    for r in p.iter(q('r')):
        t = ''.join((x.text or '') for x in r if x.tag in (q('t'), q('tab')) or x.tag == q('t'))
        if r.find(q('tab')) is not None:
            t = t + '\t'
        if not t:
            continue
        rpr = r.find(q('rPr'))
        f = lambda n: rpr is not None and rpr.find(q(n)) is not None and rpr.find(q(n)).get(q('val')) not in ('0', 'false')
        hl = rpr is not None and (rpr.find(q('highlight')) is not None or
                                  (rpr.find(q('shd')) is not None and rpr.find(q('shd')).get(q('fill')) not in (None, 'auto', 'FFFFFF')))
        va = rpr.find(q('vertAlign')).get(q('val')) if rpr is not None and rpr.find(q('vertAlign')) is not None else None
        key = (f('b'), f('i'), hl, va)
        if segs and segs[-1][0] == key:
            segs[-1][1] += t
        else:
            segs.append([key, t])
    out = ''
    for (b, i, hl, va), t in segs:
        t = re.sub(r'([*=^_\\])', r'\\\1', t)
        if va == 'superscript':
            t = '^{' + t + '}'
        elif va == 'subscript':
            t = '_{' + t + '}'
        if i:
            t = f'*{t}*'
        if b:
            t = f'**{t}**'
        if hl:
            t = f'=={t}=='
        out += t
    return out


def cmd_extract(a):
    root = ET.fromstring(read_zip(a.doc)['word/document.xml'])
    q = lambda t: f'{{{W}}}{t}'
    for p, in_tbl in iter_body_paras(root):
        txt = para_markup(p)
        ppr = p.find(q('pPr'))
        style = ppr.find(q('pStyle')).get(q('val')) if ppr is not None and ppr.find(q('pStyle')) is not None else ''
        if not txt.strip():
            print('')
            continue
        if style.lower().startswith('heading'):
            lvl = re.sub(r'\D', '', style) or '1'
            print('#' * int(lvl) + ' ' + txt)
        elif ppr is not None and ppr.find(q('numPr')) is not None:
            ilvl = ppr.find(f'{q("numPr")}/{q("ilvl")}')
            depth = int(ilvl.get(q('val'))) if ilvl is not None else 0
            print('  ' * depth + '- ' + txt)
        else:
            print(('| ' if in_tbl else '') + txt)


def cmd_inspect(a):
    parts = read_zip(a.doc)
    xml = parts['word/document.xml']
    root = ET.fromstring(xml)
    q = lambda t: f'{{{W}}}{t}'
    text = xml.decode('utf-8')
    info = {}
    s = list(root.iter(q('sectPr')))
    if s:
        pg, mar = s[-1].find(q('pgSz')), s[-1].find(q('pgMar'))
        if pg is not None:
            info['page_size_dxa'] = [pg.get(q('w')), pg.get(q('h'))]
        if mar is not None:
            info['margins_dxa'] = {k: mar.get(q(k)) for k in ('top', 'right', 'bottom', 'left')}
    info['two_column_tables'] = []
    for tbl in root.iter(q('tbl')):
        cols = [g.get(q('w')) for g in tbl.iter(q('gridCol'))]
        if len(cols) == 2:
            info['two_column_tables'].append(cols)
    heads = []
    for p, in_tbl in iter_body_paras(root):
        if in_tbl:
            continue
        t = ''.join(x.text or '' for x in p.iter(q('t'))).strip()
        hl = any(True for _ in p.iter(q('highlight')))
        if t and (hl or re.match(r'(?i)^(topic|week|module|lecture|chapter|unit|part)\s*\d', t)):
            heads.append(t)
    info['topic_headings'] = heads
    counts = {}
    for lab in ['KEY', 'METHOD', 'EVIDENCE', 'APPLY', 'RULE', 'TEST', 'CASE', 'POLICY']:
        n = len(re.findall(rf'<w:t xml:space="preserve">{lab} </w:t>', text))
        if n:
            counts[lab] = n
    info['tag_label_counts'] = counts
    info['label_set_in_use'] = ('law' if any(k in counts for k in ('RULE', 'TEST', 'CASE', 'POLICY'))
                                else 'generic' if counts else 'none (old-format or tagless)')
    info['has_key_line'] = bool(re.search(r'>Key: <', text))
    info['has_quick_recall'] = 'QUICK RECALL' in text
    fonts = {}
    for m in re.findall(r'w:rFonts w:ascii="([^"]+)"', text):
        fonts[m] = fonts.get(m, 0) + 1
    info['run_fonts'] = fonts
    info['has_numbering_part'] = 'word/numbering.xml' in parts
    print(json.dumps(info, indent=1, ensure_ascii=False))


def estimate_pages(doc_xml):
    root = ET.fromstring(doc_xml)
    q = lambda t: f'{{{W}}}{t}'
    s = list(root.iter(q('sectPr')))
    ph, usable = 16838, 15704
    if s and s[-1].find(q('pgSz')) is not None:
        ph = int(s[-1].find(q('pgSz')).get(q('h')))
        mar = s[-1].find(q('pgMar'))
        usable = ph - int(mar.get(q('top'), 1440)) - int(mar.get(q('bottom'), 1440)) if mar is not None else ph - 2880
    line = 269

    def plines(p, width):
        t = ''.join(x.text or '' for x in p.iter(q('t')))
        cpl = max(20, (width - 600) // 100)
        return max(1, math.ceil(len(t) / cpl))
    total = 0
    topics = []           # [title, lines] per topic, a topic being a highlighted title plus its table
    body = root.find(q('body'))
    for el in body:
        if el.tag == q('p'):
            n = plines(el, 10000)
            total += n
            t = ''.join(x.text or '' for x in el.iter(q('t'))).strip()
            if t and any(True for _ in el.iter(q('highlight'))):
                topics.append([t, 0])
            if topics:
                topics[-1][1] += n
        elif el.tag == q('tbl'):
            for tr in el.iter(q('tr')):
                hs = []
                for tc in tr.findall(q('tc')):
                    w = tc.find(f'{q("tcPr")}/{q("tcW")}')
                    width = int(w.get(q('w'))) if w is not None else 5000
                    hs.append(sum(plines(p, width) for p in tc.findall(q('p'))))
                total += max(hs or [1])
                if topics:
                    topics[-1][1] += max(hs or [1])
    scale = line / usable
    return total * scale, [(t, n * scale) for t, n in topics]


def pdf_page_count(path):
    if shutil.which('pdfinfo'):
        out = subprocess.run(['pdfinfo', path], capture_output=True, text=True).stdout
        m = re.search(r'^Pages:\s+(\d+)', out, re.M)
        if m:
            return int(m.group(1))
    return len(re.findall(rb'/Type\s*/Page[^s]', open(path, 'rb').read()))


def cmd_pages(a):
    est, topics = estimate_pages(read_zip(a.doc)['word/document.xml'])
    n = None
    soffice = shutil.which('soffice') or shutil.which('libreoffice')
    if soffice:
        tmp = tempfile.mkdtemp()
        try:
            subprocess.run([soffice, '--headless', '--convert-to', 'pdf', '--outdir', tmp, a.doc],
                           stdout=subprocess.DEVNULL, stderr=subprocess.DEVNULL, timeout=180)
            pdfs = [f for f in os.listdir(tmp) if f.endswith('.pdf')]
            if pdfs:
                n = pdf_page_count(os.path.join(tmp, pdfs[0]))
                if a.keep_pdf:
                    shutil.copy(os.path.join(tmp, pdfs[0]), a.keep_pdf)
                    print(f'PDF saved to {a.keep_pdf}')
        finally:
            shutil.rmtree(tmp, ignore_errors=True)
    if n is not None:
        print(f'PAGES: {n} (rendered with LibreOffice)')
    else:
        print('PAGES: unknown (LibreOffice not available; open the file to confirm)')
    print(f'CONTENT ESTIMATE: about {est:.1f} pages (rough guide to how full the pages are)')
    if len(topics) > 1:
        for t, t_est in topics:
            print(f'  topic "{t[:60]}": about {t_est:.1f} pages')
    if a.cap:
        cap = a.cap
        if len(topics) > 1:
            print(f'CAP READING: {cap} page(s) is treated here as the total for all {len(topics)} topics. '
                  f'If the student meant per topic, measure each topic against the cap instead. State the reading in the reply.')
        if n is not None and n > cap:
            if est <= cap:
                print(f'OVER CAP: renders at {n} pages but the content estimate is under {cap}. A whole row has probably '
                      f'jumped to the next page and left a gap: reorder rows or lower "keep_whole_lines" (e.g. 12) '
                      f'and rebuild before cutting any content.')
            else:
                print(f'OVER CAP: {n} pages against a cap of {cap}. Trim in the Step 6 order, starting with framing lines.')
        elif n is not None and est > 0.92 * cap:
            print(f'WITHIN CAP when rendered, but the last page is close to full. Word may wrap differently from '
                  f'LibreOffice: look at the last page and keep a few lines of margin.')
        elif n is None and est > 0.92 * cap:
            print(f'AT RISK: the content estimate is close to or over the {cap}-page cap and nothing was rendered to '
                  f'confirm it. Trim lightly or check the page count in Word.')
        else:
            print(f'WITHIN CAP: {cap} page(s).')
        if (n is None or n <= cap) and est < 0.8 * cap:
            print(f'UNDER-FILLED: the notes use about {est:.1f} of {cap} pages. Before delivering, undo any squeezing: '
                  f'restore sub-headings, glosses, split rows and QUICK RECALL lines, and check nothing was skipped.')


def main():
    ap = argparse.ArgumentParser(description=__doc__, formatter_class=argparse.RawDescriptionHelpFormatter)
    sp = ap.add_subparsers(dest='cmd', required=True)
    b = sp.add_parser('build'); b.add_argument('--data', required=True); b.add_argument('--out', required=True)
    b.add_argument('--page', choices=['A4', 'Letter', 'a4', 'letter'])
    p = sp.add_parser('append'); p.add_argument('--data', required=True); p.add_argument('--doc', required=True)
    p.add_argument('--out', required=True)
    i = sp.add_parser('inspect'); i.add_argument('--doc', required=True)
    e = sp.add_parser('extract'); e.add_argument('--doc', required=True)
    g = sp.add_parser('pages'); g.add_argument('--doc', required=True); g.add_argument('--keep-pdf')
    g.add_argument('--cap', type=int, help='page cap the student set')
    a = ap.parse_args()
    {'build': cmd_build, 'append': cmd_append, 'inspect': cmd_inspect,
     'extract': cmd_extract, 'pages': cmd_pages}[a.cmd](a)


if __name__ == '__main__':
    main()
```