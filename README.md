# PaperPilot — PDF2CBT-style CBT workspace

An independent React + Vite application for turning PDF question papers into timed practice tests. PDF pages are rendered in-browser with PDF.js; question crops and test data stay local to the browser.

## Features
- PDF upload and page navigation; drag to crop individual question images.
- Editable MCQ, MSQ, and numerical-answer questions with subject, section, marks, negative marks, answer key, and explanation.
- Save tests locally, import/export JSON, run timed tests, navigate with a question palette, mark for review, clear answers, and auto-submit at timeout.
- Results summary, correctness/accuracy, answer-by-answer review, and attempt history.
- Responsive layout and Vercel SPA rewrite.

## Run locally
Requires Node.js 20+.
```bash
npm install
npm run dev
```
Build with `npm run build`; Vite output is `dist`.

## Vercel
Import this repository into Vercel. Framework: Vite; build command: `npm run build`; output directory: `dist`.

## Test JSON
The app exports `{ meta: { title, durationMinutes }, questions: [...] }`. Questions support `type: "mcq" | "msq" | "nat"`, `text`, `image` (data URL), `options`, `answer` (0-based option index, array of indexes for MSQ, or string for NAT), `marks`, `negativeMarks`, `subject`, `section`, and `explanation`. Import accepts this format and arrays of question objects.

## Privacy and limits
No backend or account is required. Data is stored in localStorage; export backups regularly. Crop-based authoring is intentional because automatic question detection can misread multi-column papers and diagrams. OCR/AI extraction is not included in this version.
