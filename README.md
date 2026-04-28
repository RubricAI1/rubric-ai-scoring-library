# Rubric AI — Open Scoring Rubric Library

> 114 official essay scoring rubrics from College Board (AP), IBO (IB Diploma + MYP + PYP), Cambridge International, AQA, Edexcel, OCR, ETS, British Council, GMAC, ACT, LSAC, and NYSED — structured, source-linked, and free to use.
>
> [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) [![Rubrics](https://img.shields.io/badge/rubrics-114-blue)](#rubric-coverage) [![Exam Boards](https://img.shields.io/badge/exam_boards-13-green)](#rubric-coverage)
>
> ## Why this exists
>
> AI essay graders are everywhere. Almost none of them use the actual rubric the exam board uses. The result: vibes-based grades, and students who think they're scoring 6/6 on AP Lang Synthesis until they get a 3 on the real exam.
>
> This dataset is the source-of-truth scoring criteria for every major essay-based exam, structured for prompt injection, version-pinned, and citation-ready.
>
> It powers [Rubric AI](https://rubricai.us) — but the dataset is yours to use under MIT license.
>
> ## Rubric coverage
>
> | Exam Board | # Rubrics | Examples |
> |---|---|---|
> | College Board (AP) | 59 | AP Lang Synthesis, AP Lit Poetry, APUSH DBQ, AP Psych AAQ/EBQ, AP Calc, AP Bio, AP Spanish |
> | IB Diploma | 19 | English A Lang & Lit Paper 1+2, IB History Paper 1+2+3, TOK Essay, Extended Essay, ESS |
> | IB MYP + PYP | 13 | MYP Lang & Lit, Sciences, Math, Personal Project, Community Project, PYP Exhibition |
> | Cambridge International | 3 | IGCSE English, IGCSE Literature, A-Level Literature |
> | AQA / Edexcel / OCR | 5 | A-Level English Lit, English Language, History |
> | ETS | 4 | GRE Issue, GRE Argument, TOEFL Independent, TOEFL Integrated |
> | British Council | 3 | IELTS Task 1 Academic, Task 1 General, Task 2 |
> | Other | 8 | SAT Essay, ACT Writing, GMAT AWA, LSAT Writing, NY Regents, Common App, Universal Rubric |
> | **Total** | **114** | across 13 exam boards |
>
> ## Anti-inflation grading prompt (the secret sauce)
>
> The hardest part of LLM essay grading isn't the rubric — it's stopping the model from giving away points. Here's the prompt prefix that fixed inflation in our testing:
>
> ```
> You are an AP/IB exam-style grader. Score this essay against the OFFICIAL rubric below row-by-row.
>
> RULES:
> (a) Apply each band descriptor verbatim. Quote the exact band language for each row score.
> (b) Never award a row score higher than the band descriptor explicitly allows.
> (c) If the response straddles two bands, choose the LOWER band by default.
> (d) Do not award the sophistication/complexity point unless the essay clearly demonstrates ALL the qualifying behaviors named in the rubric — avoid "gift" points.
> (e) Cite specific evidence from the essay (with quote) for every row score.
> (f) If a row's evidence threshold is not met (e.g., "3 of 6 sources", "2 documents with HIPP"), award the corresponding lower band, not the higher.
> (g) Output the official score AND a brief rationale per row, then the final total.
> ```
>
> This produces grades that match real examiners much more reliably than vibes-based scoring.
>
> ## Citation
>
> If you use this dataset in research or a product, please cite:
>
> > Berns, K. (2026). Rubric AI: An open library of 114 official essay scoring rubrics across 13 exam boards. https://github.com/RubricAI1/rubric-ai-scoring-library
> >
> > ## Contributing
> >
> > PRs welcome:
> >
> > - New rubrics not yet covered (state Common Core, IB Math AA/AI Paper 3, IB Visual Arts, AS-Level subjects)
> > - - Year updates when exam boards publish new scoring guidelines
> >   - - Translations of rubrics to other languages
> >     - - Bug fixes in band descriptor extraction
> >      
> >       - For each rubric you add, please include the source URL and verify against the official PDF.
> >      
> >       - ## License
> >      
> >       - MIT. Use freely. Attribution appreciated but not required.
> >
> > The rubrics themselves are public domain (or in some cases, fair-use educational reproduction of publicly-released scoring guidelines). The structured dataset and tooling around them are MIT.
> >
> > ## What this is not
> >
> > - Not a substitute for human grading or teacher feedback
> > - - Not officially endorsed by College Board, IBO, Cambridge, ETS, or any exam board
> >   - - Not a guarantee of exam scores — predicted scores are estimates only
> >     - - Not legal/educational advice; rubrics may update year-to-year
> >      
> >       - ## Links
> >      
> >       - - Live AI grader: https://rubricai.us
> >         - - Rubric library (browseable): https://rubricai.us/rubrics
> >           - - Issues / new rubric requests: GitHub issues
> >             - - Contact: blakeberns@rubricai.us
