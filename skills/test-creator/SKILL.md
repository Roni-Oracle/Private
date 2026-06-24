---
name: test-creator
description: Create Hebrew multiple-choice exams from supplied course materials, including test blueprinting, balanced cognitive levels, plausible distractors, answer-key generation, RTL Hebrew formatting, browser quiz UI generation, and quality control. Use when the user asks to generate, review, improve, split into versions, or turn into an interactive UI / HTML quiz an American-style / multiple-choice / רב-ברירה / מבחן אמריקאי exam in Hebrew, especially from learning materials, syllabi, slides, summaries, articles, transcripts, or NotebookLM-style source material.
---

# Test Creator

## Core Rule

Base every question only on the supplied learning materials. Do not invent facts, examples, course emphases, terminology, or source claims. If essential source material is missing, state the gap and continue only when a useful, clearly bounded exam can still be produced.

## Default Output

Unless the user requests another scope, create one Hebrew multiple-choice exam. If the user requests multiple versions, make each version different but equivalent in coverage, difficulty, and cognitive level.

Use this default item format:

```text
1. [גוף השאלה?]
א. [אפשרות]
ב. [אפשרות]
ג. [אפשרות]
ד. [אפשרות]
```

Include a separate answer key for the examiner only. If the user asks for a student version, omit the answer key from that version.

When the user asks for a UI, quiz app, browser version, shareable file, or interactive exam, create a single self-contained `.html` file by default. The HTML file must work from `file://` with no server or internet.

## Workflow

1. Analyze the supplied sources before writing questions:
   - Identify major learning units, topics, subtopics, concepts, theories, processes, and distinctions between similar concepts.
   - Identify expected student confusions.
   - Map which topics fit knowledge, comprehension, application, analysis, evaluation, or integration questions.
   - Estimate the relative weight of each topic from source volume and centrality. Mark the estimate as approximate when the sources do not give explicit weights.

2. Build a test blueprint before drafting:
   - Cover all central course material in every standalone exam version.
   - Avoid versions that focus on only one part of the course.
   - For an 80-question exam, use the reference targets unless the course justifies a different distribution.
   - Read `references/quality-checklists.md` when you need the full blueprint and QA tables.

3. Draft questions:
   - Test one clear learning objective per question.
   - Make the stem clear and answerable before reading the options.
   - Use one correct or best answer only.
   - Use three wrong but plausible distractors that represent real misunderstandings.
   - Avoid double negatives, trick wording, vague phrasing, trivia, and external knowledge.
   - Avoid "all answers are correct", "no answer is correct", "both A and B", and similar combination options except in rare justified cases.

4. Enforce answer-option fairness:
   - Make all four options similar in length, specificity, grammar, and style.
   - Treat option-length imbalance as a serious technical clue. Do not let the correct answer be noticeably longer, more detailed, more qualified, or more academically polished than the distractors.
   - When one option must contain a technical qualifier, add comparable qualifiers or detail to the other options.
   - Prefer parallel syntax: same grammatical opening, same level of abstraction, and similar use of examples.
   - Check that option endings match the stem grammatically, so one option is not exposed by agreement, tense, gender, number, or syntax.

5. Write high-quality distractors:
   - Base distractors on confusion between close concepts, overgeneralization, partial understanding, correct model in wrong context, cause-effect reversal, plausible misreading of a case, or unsupported but tempting inference.
   - Do not use absurd, off-topic, overlapping, stylistically different, or obviously absolute distractors.
   - Avoid absolute words such as "תמיד", "לעולם", "בהכרח", or "רק" when they reveal the option as wrong.
   - Replace any distractor that does not represent a realistic misunderstanding.

6. Include case questions where appropriate:
   - Use concise, relevant scenarios with enough information to solve.
   - Avoid unnecessary reading load.
   - Test use of the material, not merely term recognition.
   - Do not prepend generic context phrases such as "במהלך פגישה טיפולית", "בבחירת התערבות", "בהערכת התקדמות", "כאשר מטופל מתאר קושי", or "במקרה של מטופל" unless that context is specific, source-grounded, and necessary to answer the item. Generic prefixes confuse examinees and can make an otherwise direct question clinically inaccurate.

7. Balance the answer key:
   - For 80 questions, aim for about 20 correct answers each for א, ב, ג, ד.
   - Avoid long runs of the same answer.
   - Avoid predictable patterns such as א, ב, ג, ד repeated.
   - For multiple versions, avoid overly similar answer-key patterns.

8. Run quality control and revise:
   - Review every question for source grounding, clarity, one best answer, distractor quality, fairness, independence, and absence of technical clues.
   - Review the full exam for coverage, difficulty, cognitive level, duplicated objectives, answer distribution, Hebrew consistency, and RTL formatting.
   - Fix problems directly. Do not merely report them.
   - After each fix, re-check that the answer key still matches the revised question.

## Interactive Hebrew Quiz UI

When creating a browser UI from a Hebrew exam:

1. Prefer a single self-contained `.html` file with inline CSS, embedded question data, and inline JavaScript.
2. Set `<html lang="he" dir="rtl">` and `<meta charset="utf-8">`.
3. Use real UTF-8 Hebrew strings for every UI label, title, button, feedback message, progress label, and summary label. Do not generate UI text through a shell path that can replace Hebrew with question-mark mojibake.
4. If generating the file via PowerShell or another shell, write with an explicit UTF-8 path and verify the written file, not only the source template.
5. For robust extraction, detect Hebrew option letters by Unicode code points for א, ב, ג, ד when shell quoting or regex literals may corrupt Hebrew text.
6. Build the interface as an actual exam surface: one question at a time, four radio options, submit button, immediate correct/incorrect feedback, next button, back button, progress indicator, score, and final missed-question review.
7. For multi-version or multi-exam quiz UIs, include an end-of-exam achievement dashboard that summarizes all exam attempts in the file: per-exam completion, per-exam score, total answered questions, total correct answers, overall accuracy, and a way to return to a specific exam/question. Preserve the final missed-question review for the current exam.
8. Keep the answer key embedded only because the local quiz needs it for grading. Warn that the HTML is appropriate for practice or quality review, not for a secure proctored exam.
9. Read `references/ui-html-checklist.md` before final delivery of an interactive UI.

## Hebrew And RTL Requirements

Write in correct Hebrew for right-to-left readers:

- Use Hebrew option letters: א, ב, ג, ד.
- Keep headings, stems, options, tables, and numbering right-aligned when the output format supports it.
- Use consistent Hebrew terminology throughout.
- Do not leave spaces before commas, periods, colons, or question marks.
- Use one space after punctuation where Hebrew prose requires it.
- Avoid double spaces and awkward line breaks.
- When inserting English terms, integrate them naturally into the Hebrew sentence and check punctuation direction.
- For HTML output, verify the rendered or written file contains no repeated question-mark mojibake in UI text. This catches encoding loss in titles, buttons, feedback, progress labels, and summaries.

## Multi-Version Exams

When creating several versions:

- Do not duplicate questions across versions.
- Do not reuse a question with only cosmetic wording changes.
- Test the same learning objective from different angles: definition, concept distinction, case identification, application, analysis, or error detection.
- Keep versions equivalent in coverage, cognitive level, difficulty, reading load, and case-question share.
- Avoid reusing the same examples or cases too often.

## Delivery Format

For each exam, include:

1. Title: `מבחן מספר X`
2. Course name if known.
3. Number of questions.
4. Student instructions: choose the best answer and mark one answer only.
5. Numbered questions.
6. Examiner-only answer key.
7. Short QA report listing coverage, cognitive-level balance, difficulty balance, number of revised/replaced questions, and remaining limitations if any.

For an interactive UI, deliver the single `.html` file first. Mention that it can be shared as an attachment and opened in Chrome, Edge, or another modern browser.

If the requested output is too long, do not reduce quality. First provide the blueprint, then produce exams in clearly labeled batches while preserving the same QA standard.
