# AI in the Office, with Guardrails

> **A practical guide to using Spec-Driven Development (SDD) for office work**  
> Not everyone uses AI inside an IDE. Many teams use ChatGPT or Claude for everyday work: reviewing contracts, structuring requests, processing assets, drafting summaries, and standardising repeatable tasks.
>
> This is **SDD translated into prompts**: a light, safe way to make AI more reliable **without extra tooling**. The idea is simple: before asking the model to _do the task_, define the task clearly enough that it can be repeated, reviewed, and trusted.

---

## What this means in practice

For office work, **SDD is not about software engineering jargon**. It is about turning vague requests into repeatable operating instructions.

Instead of saying:

- “Crop these images”
- “Find the key points in this contract”
- “Summarise this document”

…you define a small spec first:

- **Goal** — what the task is
- **Inputs** — what material the AI will receive
- **Output** — what it must return
- **Rules** — what must always happen
- **Exceptions** — what to do when the input is messy or incomplete
- **Done** — what counts as complete

That is SDD in office form.

---

## Why this is useful for leaders and teams

A spec-driven prompt helps with things CEOs, operations leads, legal teams, and assistants care about:

- more **consistent outputs**
- fewer hidden assumptions
- easier delegation
- clearer review standards
- better compliance with internal ways of working
- less “AI improvisation”

It also makes prompts easier to share across a team.

---

## Basic pattern

A good office-task prompt usually includes:

- **Task context**
- **Current input type**
- **Desired output**
- **Rules and constraints**
- **Escalation / exception handling**
- **Review standard**

In one line:

> **SDD for office work = define the task before asking the AI to perform it.**

---

## Example 1 — Image cropping

### Weak prompt

```text
Crop these images to 1080 x 1350.
```

This leaves too much undefined:

- Can it cut off faces?
- Should it preserve text or logos?
- What if the subject is off-centre?
- What if one image cannot be cropped cleanly?

### Better, spec-driven prompt

```text
I want to standardise this image task using a spec-driven approach.

Do not start editing immediately.
First, restate the task as a short operational spec.

Task:
Crop a batch of existing images to 1080 x 1350.

Requirements:
- Final size must always be 1080 x 1350
- Preserve the main subject whenever possible
- Do not crop faces awkwardly
- Do not cut off important text or logos
- Prefer trimming background or empty space first
- Keep visual consistency across the batch
- If an image cannot be cropped cleanly, flag it instead of forcing a bad result

Output format:
1. Short task spec
2. Cropping rules
3. Edge cases to watch for
4. Final execution checklist

After that, give me a reusable prompt version I can use again for future batches.
```

### Reusable execution prompt

```text
Use this image-cropping spec for the attached batch.

Goal:
Produce final images at 1080 x 1350.

Rules:
- Preserve the main subject
- Avoid awkward cuts on faces, hands, and text
- Prefer removing background space first
- Keep the batch visually consistent
- Flag any image that cannot be cropped cleanly

For each image, return:
- status: cropped / flagged
- short note if flagged
- output filename suggestion

Do not improvise new rules.
Follow the spec exactly.
```

---

## Example 2 — Contract key points

### Weak prompt

```text
Summarise this contract.
```

This is risky because “summary” changes every time.

### Better, spec-driven prompt

```text
I want to standardise contract review in a spec-driven way.

Do not summarise the contract yet.
First, define the extraction spec for "key points".

Task:
Review contracts and extract the same core decision points every time.

The key points must include:
- Parties
- Effective date
- Term
- Renewal
- Termination
- Payment terms
- Liability / limitation of liability
- Confidentiality
- Intellectual property
- Exclusivity / non-compete
- Governing law / jurisdiction
- Notice periods
- Unusual clauses
- Red flags
- Missing or unclear items

Output format:
1. Short operational spec
2. Extraction framework
3. Risk categories
4. Reusable review template

Important:
- Be precise
- Prefer clause-based extraction over vague summary
- Separate factual extraction from interpretation
```

### Reusable execution prompt

```text
Review the attached contract using the approved extraction spec.

Instructions:
- Extract the key points under the agreed headings
- Keep factual extraction separate from risk commentary
- Quote only short supporting snippets where useful
- Flag unclear, missing, or unusual clauses
- Add a final section called "Practical watchouts"

Return the output in this structure:
1. Contract snapshot
2. Key points
3. Risks / red flags
4. Missing or unclear items
5. Practical watchouts
```

---

## A simple template for office use

```text
I want to handle this task using a spec-driven approach.

Before doing the work, first turn the request into a short operational spec.

Task:
- [what needs to be done]

Inputs:
- [what files, images, contracts, emails, or documents will be provided]

Required output:
- [what the AI must return]

Rules:
- [what must always happen]
- [what must never happen]

Exceptions:
- [what to do if the input is incomplete, messy, ambiguous, or low quality]

Definition of done:
- [what counts as complete]

Then:
1. Write the short spec
2. Show the checklist
3. Produce a reusable execution prompt

Do not improvise requirements that are not stated.
Flag assumptions clearly.
```

---

## Policy and governance note

For business use, this matters.

Before using AI on real company materials, teams should align on a few basics:

- Do not upload confidential or regulated material unless company policy allows it
- Treat AI output as a draft, not as final authority
- Keep human review for legal, financial, HR, and customer-facing decisions
- Use standard headings and review templates so outputs are auditable
- If the task requires judgement, separate **facts extracted** from **interpretation**

A good prompt improves quality. It does **not** replace governance.

---

## Short takeaway

**SDD is useful outside engineering.**

For office work, it means turning repeatable tasks into small, reusable specs so the AI works with:

- clearer instructions
- fewer surprises
- more consistent output
- easier review by humans

That is the real value:

> **less prompting theatre, more operational clarity.**
