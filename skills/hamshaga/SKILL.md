---
name: hamshaga
description: create structured hebrew cbt case conceptualizations (hamshaga) for training, supervision, or clinical demonstration from patient information and optional template/example documents. use when asked to build, complete, refine, critique, or format a cbt formulation in the course style, including childhood and life experiences, core beliefs, conditional assumptions, rules, biased expectations, representative events, automatic thoughts, emotion intensity, fight-flight-freeze responses, maintenance summary, missing information, strengths, and evidence against.
---

# המשגה

## Purpose
Produce a course-style Hebrew CBT case conceptualization that is clinically careful, structured, and teachable. The output must make the cognitive-behavioral chain visible rather than merely list symptoms.

## Operating principles
- Write the final formulation in Hebrew unless the user explicitly requests another language.
- Preserve the course hierarchy: life experiences -> core beliefs -> assumptions -> rules -> biased expectations -> representative events -> automatic thoughts -> emotions -> behavior/fff -> integrative maintenance summary.
- Use the patient's own wording whenever supplied. Keep vivid automatic thoughts in first person.
- Do not invent missing facts. Mark gaps explicitly under `מידע חסר` or inside the relevant section as `השערה בלבד` when using a cautious inference.
- Use tentative clinical language for developmental links: `ייתכן`, `עשוי היה לתרום`, `נראה ש`, `אפשר לשער`.
- Avoid blaming parents or environments. Describe learning histories and schema formation, not fault.
- Include strengths, resources, exceptions, and evidence against the schema when available.
- Prefer one to three central core beliefs that explain multiple current triggers.
- Choose two representative events that show the same underlying mechanism from different angles when possible. Good pairings are: past + present, work + relationship, exposure + failure, criticism + uncertainty.

## Required workflow
1. **Extract facts and separate inference.** Identify developmental events, current triggers, emotions, behaviors, safety behaviors, avoidance, interpersonal context, body sensations, strengths, and exceptions.
2. **Build the schema hypothesis.** Ask: what painful meaning does the patient repeatedly fear will be proven about them?
3. **Translate the schema into course categories.** Keep each level distinct:
   - core beliefs are short identity statements beginning with `אני...`.
   - conditional assumptions use `אם... אז...` or `בגלל ש/בגלל שאני... אז...`.
   - rules use `אני חייב/ת`, `אני צריך/ה`, `אסור לי`.
   - biased expectations are impossible or overgeneralized expectations about self, others, or the world, often with `כולם`, `כל`, `תמיד`, `אף פעם`, `העולם`.
4. **Analyze representative events.** For each event include a concrete situation, automatic thoughts, emotional response with intensity percentage, behavioral/fff response, and a short formulation note connecting the event to the schema.
5. **Write a synthesis.** Explain how the pattern is maintained: trigger -> threat meaning -> emotion/body response -> fight/flight/freeze/safety behavior -> short-term relief -> long-term maintenance cost.
6. **Quality check.** Verify that no section is diagnostic filler, every assumption links to a core belief, and every event demonstrates the same mechanism.

## Default output structure
Use this structure unless the user provides a different blank form.

```markdown
# המשגה - [שם המטופל/ת] - [תאריך]

## חוויות ילדות ואירועי חיים רלוונטיים
[Only relevant developmental/life events. For each, describe how it may have contributed to a belief or coping rule. Include resources and counter-evidence when relevant.]

## אמונות יסוד
- אני...
- אני...

## הנחות בסיס - הצהרות שליליות
- אם... אז...
- בגלל שאני/ש... אז...

## חוקים וכללים
- אני חייב/ת...
- אני צריך/ה...
- אסור לי...

## ציפיות מוטות
### מעצמי
- ...
### מאחרים
- ...
### מהעולם/מהמציאות
- ...

## אירועים מייצגים
### אירוע 1 - [כותרת קונקרטית]
**אירוע:** ...
**מחשבות אוטומטיות:** ...
**תגובה רגשית + עוצמה:** חרדה __%, בושה __%, אשמה __%, ייאוש __% וכו'.
**תגובה התנהגותית fff:** Fight/Flight/Freeze + description of the visible or internal response.
**סיכום האירוע:** how this event demonstrates the schema and maintenance cycle.

### אירוע 2 - [כותרת קונקרטית]
**אירוע:** ...
**מחשבות אוטומטיות:** ...
**תגובה רגשית + עוצמה:** ...
**תגובה התנהגותית fff:** ...
**סיכום האירוע:** ...

## סיכום
[Integrative paragraph: in which situations the system is triggered, what core fear is activated, what automatic thoughts and emotions arise, what protective behaviors follow, why they help in the short term, and how they maintain the difficulty in the long term.]

## מידע חסר
[Use only when needed. List missing details that would improve confidence.]
```

## Event-analysis standards
- The event must be specific, not a broad category. Write `קיבלה מייל עם הכותרת...` rather than `בעבודה`.
- Automatic thoughts must sound like the patient's mind in the moment, not like therapist interpretation.
- Emotional responses must include intensity in percent when the data is available. If not available, estimate only if the user allows estimates; otherwise mark missing.
- FFF may be external or internal. Internal fight can be harsh self-criticism. Flight can be avoidance, reassurance seeking, checking, postponement, closing a message, or mentally escaping. Freeze can be blanking, stuckness, indecision, body shutdown, or inability to organize action.
- The event summary should show the bridge between the immediate thought and the deeper belief.

## Handling insufficient information
When patient data is too thin, do not produce a confident full formulation. First provide a partial formulation and a concise list of targeted questions. Prioritize questions about:
- two concrete recent trigger events;
- exact automatic thoughts in first person;
- emotions and intensity;
- what the patient did next, including safety behaviors;
- childhood/life experiences that taught similar meanings;
- strengths, exceptions, and evidence against the feared belief.

## Common quality problems to avoid
- Turning the childhood section into a full biography.
- Writing many disconnected core beliefs instead of one coherent schema hypothesis.
- Confusing rules with assumptions.
- Writing biased expectations that are merely ordinary preferences rather than rigid, impossible expectations.
- Omitting the short-term benefit of avoidance or safety behavior.
- Making the summary sound moralizing. The summary should normalize protective behavior while showing its maintenance cost.
