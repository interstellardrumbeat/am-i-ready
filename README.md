# Am I Ready? — Readiness Diagnostics for the new academic year

**Am I Ready?** is a collection of browser-based diagnostic tools designed to help students check whether they have the prerequisite needed before starting a new class or course (currently only for maths classes).

The aim is not to predict a grade. Instead, each diagnostic is intended to identify strengths, gaps, misconceptions, and areas that may be worth reviewing with a teacher or tutor before the next course begins.

## Available diagnostics

| Transition | Diagnostic | Audience | Approx. time |
| --- | --- | --- | --- |
| Grade 8 → Grade 9 | Grade 8 to Grade 9 Mathematics | MYP / lower secondary | 60 minutes |
| Grade 10 / MYP 5 / GCSE → IB Diploma | IB Mathematics AA SL Readiness | IB Diploma preparation | 60 minutes |
| Grade 10 / MYP 5 / GCSE → IB Diploma | IB Mathematics AA HL Readiness | IB Diploma preparation | 60 minutes |
| Grade 10 / MYP 5 / GCSE → IB Diploma | IB Mathematics AI SL Readiness | IB Diploma preparation | 60 minutes |
| Grade 10 / MYP 5 / GCSE → IB Diploma | IB Mathematics AI HL Readiness | IB Diploma preparation | 60 minutes |

More diagnostics will be added.

## How it works

1. **Choose the transition** - select the class or course you are about to start.
2. **Complete the diagnostic independently** - the result is most useful when it reflects genuine strengths and gaps.
3. **Review the report** - use the skill profile and information to decide what should be revised, ideally with a teacher or tutor.

The homepage can be filtered by current stage or destination course, and it also includes a search box for quickly finding a diagnostic.

## Diagnostic design

The tools are designed as **readiness diagnostics**, not as tests of the course the student is about to begin.

The core questions focus on prerequisite knowledge that a student should reasonably bring into the target course. Some diagnostics also include an **optional bridge section** that samples material the student may already have encountered but that is not required for the readiness score.

Depending on the diagnostic, the tools also include:

- approximate time spent on each question;
- skill-by-skill results;
- identification of high-confidence errors;
- suggested areas for review or tutoring;
- a question-by-question summary;
- a downloadable text report.

For the IB Mathematics diagnostics, question selection is based on the relevant official IB Mathematics guides. The diagnostic questions themselves are newly written and are not copied from IB examination papers or textbooks.

## Repository structure

```text
.
├── index.html
├── diagnostics.js
├── README.md
└── tools/
    ├── grade8-to-grade9.html
    ├── ib-aa-sl.html
    ├── ib-aa-hl.html
    ├── ib-ai-sl.html
    └── ib-ai-hl.html
```

### `index.html`

The main landing page. It reads the diagnostic list from `diagnostics.js` and automatically creates the cards, filters, and search results.

### `diagnostics.js`

The central registry of available diagnostics. In most cases, adding a new diagnostic does **not** require editing `index.html`.

### `tools/`

Each diagnostic is kept as a separate HTML file. This makes individual tools easier to edit and reduces the risk of changes to one diagnostic affecting another.

## Adding a new diagnostic

Normally only two steps are required.

### 1. Add the diagnostic HTML file

Place the new file in the `tools/` directory, using a simple lowercase filename with hyphens, for example:

```text
tools/grade7-to-grade8.html
```

### 2. Add an entry to `diagnostics.js`

For example:

```js
{
  id: 'grade7-grade8',
  current: 'Grade 7',
  next: 'Grade 8',
  title: 'Grade 7 to Grade 8 Mathematics',
  description: 'Checks the prerequisite mathematics needed for a confident start to Grade 8.',
  audience: 'MYP / lower secondary',
  duration: '60 minutes',
  href: 'tools/grade7-to-grade8.html'
},
```

The homepage will then automatically include the new diagnostic in:

- the diagnostic cards;
- the **Current class / stage** filter;
- the **Moving into** filter;
- search results.

No additional homepage JavaScript is normally required.

## Running locally

There is no build process and no external framework is required.

Clone or download the repository and open `index.html` in a browser.

```bash
git clone <your-repository-url>
cd <your-repository-folder>
```

## Educational use and limitations

These tools are intended to support **diagnosis and discussion**, not to replace professional judgement.

A diagnostic result should not be treated as:

- an official school examination;
- an official IB assessment;
- a prediction of a future course grade; or
- a complete measure of a student's mathematical ability.

**Results are most useful when considered alongside the student's previous work and discussed with a teacher or tutor.**

## About

I created **Am I Ready?** as a practical way to identify prerequisite gaps before students move into a new mathematics class or course or to assist tutoring and revision sessions.

The project is designed to grow over time: new grades and classes can be added by creating a diagnostic page and registering it in `diagnostics.js`.
