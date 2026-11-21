<div align="center">

# anti-ai-slop-design

**Get distinctive UI, slide, and motion design out of Claude, not the same serif-and-orange look every time.**

![Type](https://img.shields.io/badge/type-Claude%20skill-black)
![License](https://img.shields.io/badge/license-MIT-black)
![Scope](https://img.shields.io/badge/scope-UI%20%C2%B7%20slides%20%C2%B7%20motion-black)

[Install](#install) · [The method](#the-method) · [Prompts to copy](#prompts-to-copy) · [Checklist](#checklist) · [Source](#source-and-attribution)

</div>

---

## The idea in one line

> What you put in is what you get out. Give context, ask for breadth, then converge.

Claude's default design tends to repeat itself: serif text, light gray background, orange accent, cards with a colored edge stripe. This skill is a working method for steering around that.

## Install

```bash
mkdir -p ~/.claude/skills/anti-ai-slop-design
curl -o ~/.claude/skills/anti-ai-slop-design/SKILL.md \
  https://raw.githubusercontent.com/panyuti-ai/anti-ai-slop-design/main/SKILL.md
```

Or copy `SKILL.md` into a folder named `anti-ai-slop-design` inside your skills directory.

## The method

Open each section to read the full rule. The same content lives in [`SKILL.md`](SKILL.md), which is what Claude loads.

<details open>
<summary><b>1. Start from context, not a blank request</b></summary>

- Collect inputs before generating: screenshots as a mood board, pages that feel right, past work you like, and a short statement of what the thing is and how it should feel.
- If a codebase exists, read it first (see step 4).

</details>

<details>
<summary><b>2. Diverge, then converge</b></summary>

1. Ask for about 10 options that differ in fonts, colors, and visual style.
2. Pick pieces: "I like part of #1 and part of #3. Make 5 more that are different but built on those."
3. Repeat until one direction is clear.
4. Keep every version side by side on the canvas. Copy a version before changing it instead of overwriting.

</details>

<details>
<summary><b>3. Wireframe first when the task is hard</b></summary>

- Ask for several wireframes with different layouts before any font or color decision.
- Ask Claude to name similar existing products, compare their layouts, and pick the one users already know how to use.

</details>

<details>
<summary><b>4. Existing product: recreate from code</b></summary>

- Tell Claude to read the relevant parts of the codebase and recreate the current state on the canvas, then produce variations from there.
- Do not maintain long-lived design files. Recreate from current code each time.
- To build, continue in the same session so styles, sizes, fonts, and colors carry over without translation loss.

</details>

<details>
<summary><b>5. Decide style before producing a full deck</b></summary>

For presentations, agree on the visual style first. Redoing a whole deck in the wrong style wastes tokens.

</details>

<details>
<summary><b>6. Block Claude's default look</b></summary>

- Name Claude's habits in the prompt and forbid them unless asked.
- Better: supply the brand or identity yourself (colors, fonts, tone). Brand context is a durable asset that works across models.
- If output feels corporate, say so and push: "Too corporate. Use full creative range. Make it feel like a film, not a slide deck."

</details>

<details>
<summary><b>7. Give feedback efficiently</b></summary>

- High-level direction works ("make the card list denser, no subheadings, no dividers"), as do small specifics ("reduce left padding", "align icons to cells").
- Voice notes are fine for loose thoughts.
- Use comments pinned to an element or a video timestamp instead of describing location in words. Then ask Claude to process all comments.
- Let Claude ask about 8 clarifying questions before designing. Answering is easier than guessing what a designer would ask. Allow skipping.

</details>

<details>
<summary><b>8. Motion and animation</b></summary>

- Claude can track many things at once; people cannot. Require one focal change at a time.
- Leave reading time: when text appears, ask whether people have enough time to read it before the next element, and whether their eyes are where the next action happens.
- If it looks like static slides, ask for continuous movement, such as a single line the eye follows.
- Process: storyboard (static, cheap) → a few visual style options → pick one → iterate → comment-based polish.

</details>

<details>
<summary><b>9. Dashboards</b></summary>

- Give Claude the data source (spreadsheet link, MCP connector) and ask it to "make this a dashboard". Leaving the metrics unspecified can produce useful surprises.
- Connect live data when the source supports it.
- Check numbers against their source: inspect the code Claude used to fetch each figure.

</details>

<details>
<summary><b>10. Evaluate results</b></summary>

- Prefer yes/no checks over 1-5 scores.
- Automate only basics: text overlap, and whether 10 runs all pick the same font and color.
- Taste still needs a human reviewing outputs and transcripts.
- To test a skill that produces videos or designs, run several fresh sessions that see only the skill plus a one-line request, then review the results yourself.

</details>

## Prompts to copy

<details>
<summary><b>Diverge</b></summary>

```text
Here is what we're designing and how it should feel: <description>.
Reference screenshots attached. Give me 10 options that differ in fonts,
colors, and visual style.
```

</details>

<details>
<summary><b>Converge</b></summary>

```text
None is perfect. I like <part> of #1 and <part> of #3. Make 5 more that
are different from each other but built on those.
```

</details>

<details>
<summary><b>Recreate from code</b></summary>

```text
Read the relevant parts of the codebase, recreate the current <screen> on
the canvas, then give me variations. Keep the original next to them.
```

</details>

<details>
<summary><b>Block the defaults</b></summary>

```text
You tend to overuse the same two fonts and two colors (serif text, light
gray background, orange accent, card edge stripes). Do not use them unless
I ask or it is clearly right for this design.
```

</details>

<details>
<summary><b>Motion pacing</b></summary>

```text
People can only focus on one thing at a time and read slowly. Make one
focal change at a time, and leave enough time for text to be read before
the next element appears.
```

</details>

## Checklist

- [ ] Context supplied (mood board, references, codebase)
- [ ] 10 divergent options requested, then a converged round
- [ ] Wireframes first if the layout is the hard part
- [ ] Default fonts and colors explicitly excluded, or brand supplied
- [ ] Versions kept side by side
- [ ] Motion: one focal change at a time, reading time left
- [ ] Data figures traced to source
- [ ] A human has looked at the output

## Source and attribution

This is an independent summary of practices discussed in the video "Full Tutorial: How to Fix AI Slop with Claude Design in 40 Minutes" (Peter Yang interviewing Nate Parrott): https://www.youtube.com/watch?v=604T-74s3KE

It contains no transcript text. It is not affiliated with or endorsed by the interviewer, the guest, or Anthropic. Any errors in interpretation are mine.

## License

[MIT](LICENSE)
