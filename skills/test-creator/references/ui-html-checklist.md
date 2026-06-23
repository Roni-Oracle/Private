# Hebrew Quiz UI Checklist

Use this checklist before delivering an interactive Hebrew multiple-choice exam.

## Required Behavior

- The deliverable is a single `.html` file unless the user explicitly asks for editable source files.
- The file opens locally with `file://` and does not require a server, install, or internet access.
- The quiz shows one question at a time.
- Each question has exactly four options labeled א, ב, ג, ד.
- The user must choose an answer before submitting.
- The quiz gives immediate feedback after submission.
- After a wrong answer, the UI shows the correct answer.
- The next question appears only after feedback is visible.
- A back button allows returning to the previous question without losing already submitted answers or feedback.
- For multi-version or multi-exam quiz files, the end screen includes an achievement dashboard with per-exam progress, per-exam score, overall answered count, overall correct count, overall accuracy, and navigation back into a selected exam/question.
- The final screen shows score and missed-question review with selected and correct answers. For multi-exam files, this review appears alongside or below the achievement dashboard for the current exam.

## Hebrew And Encoding

- Include `<meta charset="utf-8">`.
- Include `lang="he"` and `dir="rtl"` on the `<html>` element.
- Use actual UTF-8 Hebrew text for all static UI strings.
- Verify the final written HTML contains no repeated question-mark mojibake.
- Verify the final written HTML still contains Hebrew UI labels such as:
  - `שלח`
  - `הבא`
  - `סיום`
  - `נכון`
  - `לא נכון`
  - `סיכום המבחן`
  - `חזרה`
  - `דשבורד הישגים`
- If static UI strings become repeated question marks, do not patch the browser output manually. Regenerate or patch the HTML source using explicit UTF-8 writing and verify the file again.

## Parsing And Data Integrity

- Prefer deterministic parsing from the exam text instead of manual retyping.
- Normalize whitespace and strip direction marks.
- Split the question body before the answer-key section.
- Detect question starts sequentially from `1.` onward.
- Detect options only at the start of option lines.
- If Hebrew regex literals are unreliable in the shell, detect option letters by Unicode code points:
  - א = `0x05D0`
  - ב = `0x05D1`
  - ג = `0x05D2`
  - ד = `0x05D3`
- Verify:
  - question count matches the source,
  - option count equals question count times four,
  - every answer-key entry maps to an existing option,
  - answer distribution still matches the final key.

## UI Design

- Keep the first screen as the exam itself, not a landing page.
- Use restrained, readable styling suitable for academic practice.
- Use stable card and option dimensions so selecting an option does not shift layout.
- Keep text right-aligned and readable on mobile.
- Avoid decorative backgrounds that distract from the questions.

## Sharing Note

Tell the user the file can be shared as an attachment and opened in a modern browser. Also tell them that because answers are embedded in the HTML for grading, it is suitable for practice or review, not a secure exam.
