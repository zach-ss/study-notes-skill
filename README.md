# study-notes-skill
A free Claude skill that turns lecture slides, textbook chapters or your own rough notes into two-column Word study notes for any uni subject. Tagged key points, sub-headings, a QUICK RECALL row and page caps. Works in Claude, and as a paste-in for ChatGPT and Gemini.

## What you get

A Word document (.docx) with:

- **Two columns.** The subtopic on the left. On the right, bold sub-headings, short dash bullets and lettered lists for steps, stages and criteria.
- **A few colour tags** on the points most likely to be examined: KEY (must know), METHOD (how to apply), ★ EVIDENCE (the leading example or case) and APPLY (the practical point). Law students get RULE, TEST, CASE and POLICY instead. Tags are used sparingly on purpose.
- **A QUICK RECALL row** at the end of each topic for last-minute revision.
- **Depth that matches the idea.** Simple facts get one line. Hard, central ideas get the explanation, conditions and steps.
- **Page limits that work.** Ask for "max 2 pages" and it trims depth, not structure.

It can also reformat your own notes into the same table without rewriting your words, add a new topic to notes you already have, or tell you which topics in a textbook matter most.

## Install

### Quick start (no GitHub experience needed)

1. Open the `study-notes` folder above, click **`SKILL.md`**, then click the **copy icon** at the top right of the file.
2. Paste it into a new chat in **ChatGPT, Claude or Gemini**.
3. Attach your slides, textbook pages or notes and say what you want, for example:
   > make study notes from these slides, max 2 pages

> [!NOTE]
> **Before you start:** this needs an AI mode that can create files for you, because the Word file is built by a small script inside the chat. If yours can't, it gives you the notes as a table in the chat instead.

### Claude (recommended)

1. Download SKILL.md.
2. In Claude, open your skills settings (Customize, then Skills) and upload the zip or simply paste the SKILL.md in chat.
3. Start a chat, attach your slides or readings, and say: `use study-notes`.

### Claude Code

Copy the `study-notes` folder into your skills folder, for example `~/.claude/skills/`.

### Other tools (ChatGPT, Gemini)

These tools do not load skill folders. Open `study-notes/SKILL.md`, paste the whole file into a chat (or into a Custom GPT or Gemini Gem), and attach your material. The skill is written to treat itself as active when pasted, so you do not need to name it.

Note: the Word file is built by a small Python script included in the skill. That needs a mode that can run Python and return files. Without one, the tool should offer the same notes as a markdown table instead.

## How to use it

Attach your material, then try:

- `use study-notes, max 2 pages`
- `use study-notes on these slides, law labels`
- `use study-notes to reformat my notes into the table, keep my wording`
- `add this week's lecture to my existing notes`
- `what should I focus on in this textbook?`

## What it asks you

Before building, it asks a few quick questions only when the answer changes the result. For example:

- If you give a page limit across several topics: is it the total for everything, or per topic?
- If the readings are on unrelated subjects: one document with a new page per topic, or separate documents?
- If the limit looks tight: keep every subtopic with less depth, or drop some?

If it cannot ask (an automated run, for instance), it uses sensible defaults and tells you which ones.

## Tips

- Give it your slides and the textbook chapter together. The slides show what was taught and the textbook fills in the detail.
- A unit outline, tutorial sheets or past papers help it judge what is examined.
- If the notes are too shallow somewhere, say "go deeper on [topic]".
- Check the reply. It lists what the page limit cost, any errors it found in your sources, and any lines it was unsure about.
- Always check the notes against your course materials. It can make mistakes.

## Limitations

- Tested mainly in Claude. Results in other tools vary.
- It does not add images or diagrams. Diagrams are described in words.
- It only uses what is in your material. It does not add outside cases or citations.
- Word and LibreOffice wrap text slightly differently, so page counts can shift by a few lines.

## Files

- `study-notes/SKILL.md`: the skill, including the build script.

## Licence

MIT. Free to use, share and adapt. 

Made by Zachary Sullivan.
