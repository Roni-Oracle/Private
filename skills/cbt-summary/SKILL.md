---
name: cbt-summary
description: Analyze all available Hebrew or mixed-language CBT/LI CBT patient materials and produce a clinically cautious, focused Hebrew case summary for a therapist, optionally as a fully RTL Hebrew Word document. Use when the user asks to summarize, formulate, review, improve, or extract insights from patient treatment files, session notes, full transcripts, handwritten diaries, worksheets, presentations, tools, homework, questionnaires, recordings/transcript PDFs, or folders of therapy materials; especially for LI CBT case formulation, treatment-process summaries, current protocol stage, techniques used, cognitive patterns, triggers, avoidance, safety behaviors, core beliefs, therapeutic goals, tools learned, achievements, relapse prevention, or therapist-facing documents that may later be edited and shared with the patient.
---

# CBT Summary

## Core Rule

Produce a professional Hebrew, RTL-ready, therapist-facing document that can later be edited and shared with the patient. Base every conclusion on the supplied materials. Distinguish clearly between documented facts, clinical hypotheses, missing information, and recommendations for further assessment.

Do not diagnose formally unless the materials explicitly contain a diagnosis by a qualified clinician. When risk signals appear, surface them clearly and recommend clinician review.

## Workflow

1. Inventory all available materials before summarizing:
   - Treatment diary/session notes.
   - Full session transcripts, including transcript PDFs or recording-derived text.
   - Handwritten diaries, worksheets, thought records, monitoring diaries, exposure logs, homework, and photos/scans of clinical work.
   - Questionnaires, scales, assessment summaries.
   - Psychoeducation materials, slides, tools, handouts, and techniques introduced by the therapist.
   - Prior intake/background documents and relevant medical, family, occupational, educational, relational, or trauma history.

2. Treat transcripts and handwritten patient work as primary clinical evidence:
   - Do not dismiss transcripts as secondary or merely "not fully analyzed" if they are available. Extract/read them and use them to identify specific in-session formulations, Socratic work, patient language, turning points, therapist decisions, and homework review.
   - Do not ignore handwritten diaries because they are scans. Inspect them visually when possible. If handwriting is only partly legible, include the clinically reliable parts and mark uncertain wording cautiously.
   - Cross-check handwritten entries against transcripts/session notes before turning them into strong conclusions.
   - Avoid over-quoting uncertain handwriting. Prefer cautious wording such as "ביומן בכתב יד מופיעה מחשבה בנוסח..." or "נראה כי...".

3. Extract evidence into a working map:
   - Presenting problem and current complaint.
   - Patient-stated goals and therapist-stated treatment goals.
   - Current stage in the LI CBT protocol and which stages have already been completed.
   - Techniques/tools already taught and whether they were actually practiced.
   - Suitability for LI CBT, complexity factors, and signs that higher-intensity, specialist, medical, psychiatric, or risk-focused review may be needed.
   - Relevant history connected to the complaint.
   - Triggers, maintaining factors, avoidance, safety behaviors, rituals, reassurance seeking, checking, rumination, suppression, or other coping patterns.
   - Automatic thoughts, assumptions, rules for living, cognitive biases, core beliefs, and self/other/world beliefs.
   - Emotions, body sensations, behaviors, interpersonal patterns, and consequences.
   - Measures and outcome tracking: baseline scores, repeated scores, symptom change, functioning change, and clinically meaningful change where documented.
   - Tools taught, homework assigned, actual practice, adherence barriers, and response to intervention.
   - Successes, gains, strengths, and evidence of learning.
   - Open questions, contradictions, and missing data.

4. Read `references/report-structure.md` before drafting the final report.

5. Read `references/clinical-formulation.md` when building the CBT/LI CBT formulation.

6. When the materials include avoidance, safety behaviors, exposure planning, behavioral experiments, core beliefs, or recommendations for the next treatment phase, apply the distinction in `references/clinical-formulation.md` between:
   - Structured exposures for avoided emotion/threat, reduction of avoidance and safety behaviors, and repeatable 5-times practice.
   - Small behavioral experiments for challenging core beliefs after diary 3 / core-belief work, focused on gathering evidence about identity-level beliefs.

7. Read `references/hebrew-style-rtl.md` before finalizing Hebrew wording, headings, tables, and shareable tone.

## Report Focus

Prefer a focused clinical document over an audit trail. Do not include unnecessary meta-information about extraction, OCR, file processing, or how the summary was produced unless it changes clinical confidence.

In the opening executive summary, include:

- Presenting problem.
- Current stage in the LI CBT protocol: for example assessment, psychoeducation, monitoring, behavioral activation, cognitive restructuring, shared formulation, core-belief work, exposure/behavioral experiments, relapse prevention, or follow-up.
- Which protocol stages have already been completed.
- A concise list of techniques/tools already used.
- Current formulation in one clear maintaining cycle.
- Fit for LI CBT and cautions.
- Key measures and clinically meaningful functional change.
- Main recommendation for the next treatment phase.

When revising or reviewing an existing summary, tighten it:

- Remove repetitive source descriptions and process notes.
- Keep only clinically useful background.
- Make the formulation sharper and easier to use in supervision or treatment planning.
- Ensure recommendations follow directly from the formulation and the tools already practiced.
- Avoid duplicating exposure tasks and core-belief experiments. Put exposure work only in the avoidance/exposure map. Put core-belief experiments only in the core-belief section, and include that section only when there is a documented core belief or a strong treatment hypothesis.

## Evidence Discipline

Write in cautious clinical language:

- Prefer "מהחומר עולה כי..." for supported observations.
- Prefer "ניתן לשער..." or "השערה טיפולית אפשרית היא..." for hypotheses.
- Prefer "לא נמצא בחומר מידע מספק לגבי..." for gaps.
- Avoid inflated certainty, pathologizing language, or unsupported labels.
- Do not fill gaps with generic CBT content. If there is not enough information, produce a shorter report and list what is missing.
- If the source materials conflict, present the conflict and do not force a single interpretation.

## Required Output Qualities

- Hebrew output, full RTL orientation.
- Professional but humane tone.
- Written for the therapist, yet phrased so it could be shared with the patient after editing.
- Comprehensive when the evidence supports it; concise and focused when possible.
- Start with an executive summary on the first page.
- Include a compact "clinical caution" section when there are risk, complexity, safeguarding, medication, trauma, substance-use, psychosis-like, eating-disorder, domestic-violence, or severe impairment signals.
- Include a clear section or opening subsection for `שלבים שכבר בוצעו בפרוטוקול`.
- Include a clear section or opening subsection for `טכניקות וכלים שנעשה בהם שימוש`.
- End with two distinct sections:
  1. `ארגז כלים`: every tool, technique, worksheet, exercise, psychoeducation idea, metaphor, exposure task, behavioral experiment, or coping strategy taught during treatment.
  2. `הצלחות וחוזקות`: separate achievements gained during therapy from strengths or successes that predated therapy.

## File Handling

When materials include documents or PDFs, use the relevant document/PDF/spreadsheet skills or local tools to extract text and inspect structure. Preserve source filenames in notes only where clinically useful or needed for traceability.

When producing a `.docx`, ensure true Hebrew/RTL behavior, not just visual right alignment:

- Use a Hebrew-friendly font requested by the user; if the user gives no preference, use a professional default. If the user asks for Calibri Light, apply `Calibri Light` to all runs and styles.
- Set every Hebrew body paragraph to RTL/bidi at the paragraph XML level and align it right.
- Center headings if requested; otherwise keep a consistent Hebrew heading hierarchy.
- Set tables to RTL/bidi visual order, not only right-aligned cell text.
- Set table cells and paragraph styles to RTL/bidi as well.
- Treat English clinical terms and numbers as LTR runs inside RTL paragraphs when needed so mixed text such as `GAD-7`, `PHQ-9`, `LI CBT`, percentages, dates, and scores display in the correct order.
- Check punctuation in RTL sentences: periods, commas, colons, parentheses, quotation marks, percentages, Hebrew/English mixtures, and slash-separated scores must appear on the correct visual side.
- Do not rely on manually re-aligning text after generation; incorrect punctuation after manual alignment means the DOCX lacks true RTL settings.
- If visual render QA is unavailable, perform structural OOXML checks for paragraph `w:bidi`, right/center `w:jc`, table `w:bidiVisual`, run fonts, and deliberate LTR runs for English/numeric terms. State any render limitation transparently.

English terms such as CBT, LI CBT, PHQ-9, GAD-7, OCD, PTSD, etc. should remain in English when clinically conventional and should be protected from bidi reversal.

## Safety And Ethics

Flag urgently, without dramatizing:

- Suicidal ideation, self-harm, harm to others, abuse, neglect, coercion, psychosis-like symptoms, severe substance use, eating-disorder risk, domestic violence, medical red flags, or major deterioration.
- Medication issues only as "מידע רלוונטי לבירור רפואי/פסיכיאטרי" unless a clinician has documented more.
- Confidentiality concerns and third-party identifying details when a report may be shared.
- Indications that LI CBT may be insufficient on its own: high acute risk, severe or complex comorbidity, unmanaged trauma symptoms, severe functional collapse, repeated non-response despite adequate practice, unstable living situation, safeguarding concerns, or need for specialist protocol/supervision.

Never present the output as a substitute for clinical judgment.
