<div align="center">

<h1>peer-review-assistant</h1>

<p><b>A scored peer review, drafted by your AI editor.</b></p>

<p><i>A reviewer report has the same shape every time: four sections scored out of ten, a verdict, a few suggestions. This is that shape, plus the rules that make Cursor fill it in.</i></p>

<h6>

![Markdown](https://img.shields.io/badge/Markdown-prompts%20only-111111?style=flat-square&logo=markdown&logoColor=white)
![Cursor](https://img.shields.io/badge/Cursor-.cursorrules-6E56CF?style=flat-square)
![Code](https://img.shields.io/badge/code-none-6E56CF?style=flat-square)
![Status](https://img.shields.io/badge/status-experiment%2C%20inactive%20since%202025-555555?style=flat-square)

</h6>

<a href="#how-it-works"><b>How it works</b></a> ·
<a href="#use-it"><b>Use it</b></a> ·
<a href="#files"><b>Files</b></a>

</div>

<br>

There is no program here: three Markdown files and a rules file for the
[Cursor](https://cursor.com) editor. Paste a paper into `research.md`, ask the agent to
review it, and it writes `output.md` in the structure of a generic detailed review report,
with every score backed by examples from the paper. It was a small experiment from early 2025
and is not maintained.

## How it works

<table>
<tr>
<td width="33%" valign="top">

**1 · Paste the paper**

Replace `research.md` (an outline of a typical article: abstract, introduction, literature
review, methods, implementation, results, discussion) with the paper's text.

</td>
<td width="33%" valign="top">

**2 · Ask the agent**

`.cursorrules` tells the agent to read the paper thoroughly, copy `template.md`, and fill
each section without changing its structure.

</td>
<td width="33%" valign="top">

**3 · Read the report**

`output.md` scores the abstract, methods, findings and discussion out of 10, then gives an
overall score, a verdict and improvement suggestions.

</td>
</tr>
</table>

## The report

The template is a generic reviewer report with blanks for the venue and manuscript ID; if a
journal sends its own form, use that form's headings instead. Each score uses the same scale:

| Score | Meaning |
|---|---|
| 9-10 | Exceptional, minimal improvements needed |
| 7-8 | Strong, minor improvements possible |
| 5-6 | Average, several improvements needed |
| 3-4 | Below average, needs significant work |
| 1-2 | Poor, major revision required |

Beyond the four scored sections, the reviewer comments on literature coverage, structure,
data presentation, practical impact and reference quality.

## Use it

```bash
git clone https://github.com/parthchandak02/peer-review-assistant.git
cd peer-review-assistant
cursor .            # paste your paper into research.md
```

Then, in Cursor's agent chat, use the prompt stored in `.cursorrules`:

> Please read my research.md and template.md, then create an output.md in the format of
> template.md and with appropriate comments for research.md.

The files are plain Markdown, so the same prompt works with any AI coding agent that can
read and write the repo; copy the rules into its own instructions file.

## Files

| | |
|---|---|
| [`template.md`](template.md) | The review report: scored sections, additional considerations, verdict, suggestions |
| [`research.md`](research.md) | Placeholder for the paper under review |
| [`.cursorrules`](.cursorrules) | The prompt, workflow steps, rules and scoring scale for the agent |
| `output.md` | Written by the agent; not committed |

<br>

<div align="center">
<sub>Markdown and a Cursor rules file. No dependencies.</sub>
</div>
