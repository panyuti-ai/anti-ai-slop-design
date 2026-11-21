---
name: anti-ai-slop-design
description: Workflow and prompting rules for getting non-generic UI, slide, and motion design out of Claude. Use whenever designing or redesigning a page, app screen, deck, dashboard, or animation with Claude, especially when output looks like typical AI design (serif text, light gray background, orange accent, card with colored edge stripe) or when starting a design from scratch.
---

# Anti-AI-Slop Design

A working method for getting distinctive design from Claude. Distilled from a public interview with a designer who builds Claude's design tools. Rules below are practices, not guarantees.

## Core principle

What you put in is what you get out. Give context first, ask for breadth, then converge.

## Workflow

### 1. Start from context, not a blank request
- Collect inputs before generating: screenshots as a mood board, pages that feel right, past work that is liked, and a short statement of what the thing is and how it should feel.
- If a codebase exists, read it first (see step 4).

### 2. Diverge, then converge
1. Ask for about 10 options that differ in fonts, colors, and visual style.
2. Pick pieces: "I like part of #1 and part of #3. Make 5 more that are different but built on those."
3. Repeat until one direction is clear. Keep every version side by side on the canvas, and copy a version before changing it instead of overwriting.

### 3. Wireframe first when the task is hard
- Ask for several wireframes with different layouts before any font or color decision.
- Ask Claude to name similar existing products, compare their layouts, and pick the one users already know how to use.

### 4. Existing product: recreate from code
- Tell Claude to read the relevant parts of the codebase and recreate the current state on the canvas, then produce variations from there.
- Do not maintain long-lived design files. Recreate from current code each time.
- To build, continue in the same session so styles, sizes, fonts, and colors carry over without translation loss.

### 5. Decide style before producing a full deck
For presentations, agree on the visual style first. Redoing a whole deck in the wrong style wastes tokens.

## Prompt rules against Claude's default look

- Name Claude's habits in the prompt and forbid them unless asked: "You tend to overuse the same two fonts and two colors (serif text, light gray background, orange accent, card edge stripes). Do not use them unless the user asks or it is clearly right."
- Better: supply the brand or identity yourself (colors, fonts, tone). Brand context is a durable asset that works across models.
- If output feels corporate, say so and push: "Too corporate. Use full creative range. Make it feel like a film, not a slide deck."

## Feedback style

- High-level direction works ("make the card list denser, no subheadings, no dividers"), as do small specifics ("reduce left padding", "align icons to cells").
- Voice notes are fine for loose thoughts.
- Use comments pinned to an element or a video timestamp instead of describing location in words. Then ask Claude to process all comments.

## Clarifying questions

Let Claude ask about 8 clarifying questions before designing. Answering questions is easier than guessing what a designer would ask, and users tend to like it. Allow skipping.

## Motion and animation

- Claude can track many things at once; people cannot. Require one focal change at a time.
- Leave reading time: when text appears, ask whether people have enough time to read it before the next element, and whether their eyes are where the next action happens.
- If it looks like static slides, ask for continuous movement, such as a single line the eye follows.
- Process: storyboard (static, cheap) → a few visual style options → pick one → iterate → comment-based polish.

## Dashboards

- Give Claude the data source (spreadsheet link, MCP connector) and ask it to "make this a dashboard". Leaving the metrics unspecified can produce useful surprises.
- Connect live data when the source supports it.
- Check numbers against their source: inspect the code Claude used to fetch each figure.

## Evaluating results

- Prefer yes/no checks over 1-5 scores.
- Automate only basics: text overlap, and whether 10 runs all pick the same font and color.
- Taste still needs a human reviewing outputs and transcripts.
- To test a skill that produces videos or designs, run several fresh sessions that see only the skill plus a one-line request, then review the results yourself.

## Checklist

- [ ] Context supplied (mood board, references, codebase)
- [ ] 10 divergent options requested, then a converged round
- [ ] Wireframes first if the layout is the hard part
- [ ] Default fonts and colors explicitly excluded, or brand supplied
- [ ] Versions kept side by side
- [ ] Motion: one focal change at a time, reading time left
- [ ] Data figures traced to source
- [ ] A human has looked at the output
