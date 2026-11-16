# My contribution to CVision

**CVision** is a job-application tailoring app for the UK, built by a team of four. A user uploads their CV, pastes a job ad, and gets a CV and cover letter tailored to that ad, without the app inventing anything they did not tell it.

- **Live app:** https://cvision-eta.vercel.app
- **Repository:** https://github.com/Ali-Paybarjay/CVision
- **My merged pull requests (52, from 21 October to 12 November 2026):** https://github.com/Ali-Paybarjay/CVision/pulls?q=is%3Apr+is%3Amerged+author%3Anazaninpnhi89-oss

> A note on language: the team worked in Persian, so issue and PR titles, descriptions and commit messages are in Persian. The code, the prompts and everything in the app are in English. Each PR listed below has an English summary.

## My role

I owned the **Tailor** part of the app, from the job's requirements to the finished documents: gap questions, tailored CV, cover letter, PDF and Word export, and Apply. I also ran the **pilot programme** with real users: the feedback form and the usability test guide.

I was the second-largest contributor on the team (52 of 224 merged PRs).

## Tech stack

Next.js 16 (App Router, Server Actions), React 19, TypeScript, Zod contracts, Supabase (Postgres with row-level security), the Claude API, Vitest, Playwright, GitHub Actions and Vercel. Export uses `docx` and `pdf-lib`.

## What I built

### 1. Honest tailoring: the app never makes things up

The product promises that it never adds a skill or experience the user has not given evidence for. I built the checks that keep that promise:

- An evidence check ("Nothing invented") that compares every sentence the model writes with the user's CV and answers, ignoring invisible characters, and rejects anything without support. [#31](https://github.com/Ali-Paybarjay/CVision/pull/31), [#123](https://github.com/Ali-Paybarjay/CVision/pull/123), [#212](https://github.com/Ali-Paybarjay/CVision/pull/212)
- Every change waits for the user's approval, and each CV line can hold only one approved change. [#308](https://github.com/Ali-Paybarjay/CVision/pull/308), [#457](https://github.com/Ali-Paybarjay/CVision/pull/457)
- Guards against claims the user never made, for example an NHS Band or a professional registration such as NMC that appears only in the job ad, in suggestions, in the summary, in the cover letter and under other spellings. [#425](https://github.com/Ali-Paybarjay/CVision/pull/425), [#452](https://github.com/Ali-Paybarjay/CVision/pull/452), [#454](https://github.com/Ali-Paybarjay/CVision/pull/454), [#475](https://github.com/Ali-Paybarjay/CVision/pull/475), [#477](https://github.com/Ali-Paybarjay/CVision/pull/477), [#485](https://github.com/Ali-Paybarjay/CVision/pull/485)
- Answers like "No" or "I'm not NMC registered yet" are understood as a "No", and the app respects them everywhere. [#254](https://github.com/Ali-Paybarjay/CVision/pull/254), [#260](https://github.com/Ali-Paybarjay/CVision/pull/260), [#448](https://github.com/Ali-Paybarjay/CVision/pull/448)

### 2. The Tailor flow

- A five-step Tailor page with a live CV preview; the CV and cover letter follow one template. [#215](https://github.com/Ali-Paybarjay/CVision/pull/215)
- Gap questions about the job's requirements, worded in the job ad's own terms, generated once per job and cached so they do not use up the daily limit. [#318](https://github.com/Ali-Paybarjay/CVision/pull/318), [#405](https://github.com/Ali-Paybarjay/CVision/pull/405), [#480](https://github.com/Ali-Paybarjay/CVision/pull/480)
- A new contract field, `role` on `Job`, that keeps the profession, specialty, level and registration body from the ad so that every prompt knows the role. [#412](https://github.com/Ali-Paybarjay/CVision/pull/412), [#414](https://github.com/Ali-Paybarjay/CVision/pull/414)
- A clearer tailored CV: new section order, six skills drawn from work history, no near-duplicate skills, projects and languages, and a new line placed under the job the user named. [#259](https://github.com/Ali-Paybarjay/CVision/pull/259), [#262](https://github.com/Ali-Paybarjay/CVision/pull/262), [#255](https://github.com/Ali-Paybarjay/CVision/pull/255), [#453](https://github.com/Ali-Paybarjay/CVision/pull/453), [#459](https://github.com/Ali-Paybarjay/CVision/pull/459), [#478](https://github.com/Ali-Paybarjay/CVision/pull/478)
- A shorter cover letter where the user keeps, deletes or edits each paragraph. [#451](https://github.com/Ali-Paybarjay/CVision/pull/451)

### 3. Export, saving and Apply

- Download the tailored CV and cover letter as PDF and Word. [#82](https://github.com/Ali-Paybarjay/CVision/pull/82)
- Every CV and cover letter the user downloads or sends with Apply is saved, so they can open and download it again later. [#292](https://github.com/Ali-Paybarjay/CVision/pull/292)
- After downloading, the user can go straight to interview practice for the same job. [#289](https://github.com/Ali-Paybarjay/CVision/pull/289)

### 4. Accessibility and clear waiting

- Wait messages based on measured response times ("up to 20 seconds"), read out by screen readers, which also announce when the page is ready. [#395](https://github.com/Ali-Paybarjay/CVision/pull/395), [#455](https://github.com/Ali-Paybarjay/CVision/pull/455), [#479](https://github.com/Ali-Paybarjay/CVision/pull/479)
- When the daily limit is reached, the message says what still works, and the user's answer is kept for the next day. [#456](https://github.com/Ali-Paybarjay/CVision/pull/456)

### 5. Testing and AI evaluation

- Unit tests for the Tailor pages and logic, which never call the real model or the network.
- Seven prompt-evaluation suites in [`tests/tailor`](https://github.com/Ali-Paybarjay/CVision/tree/main/tests/tailor) that run against the real model to measure the quality of gap questions, suggestions, cover letters and the evidence check.
- A fictional nurse persona and an NHS-style Band 6 job ad as test data, so no real person's data is used. [#406](https://github.com/Ali-Paybarjay/CVision/pull/406)

### 6. Pilot programme with real users

- A feedback form that pilot users fill in after each flow, and a 15-minute usability test session guide. [#157](https://github.com/Ali-Paybarjay/CVision/pull/157), [#158](https://github.com/Ali-Paybarjay/CVision/pull/158)
- Pilot data stayed out of the repository; users were known only by codes.

## How the team worked

- Every task had a GitHub Issue, a branch named after it, and one small pull request (usually under 400 lines).
- CI on GitHub Actions ran lint, type-checking, unit tests and a build on every PR; Playwright ran an end-to-end test of the main path on a phone viewport.
- The data shapes between features lived in shared Zod contracts; changing them followed an agreed process.
- Each author reviewed their diff with an AI code reviewer, fixed what it found, and squash-merged once CI was green.

## Where to look in the code

- [`src/features/tailor`](https://github.com/Ali-Paybarjay/CVision/tree/main/src/features/tailor): Tailor logic (evidence check, suggestions, cover letter, export)
- [`src/app/tailor`](https://github.com/Ali-Paybarjay/CVision/tree/main/src/app/tailor): Tailor pages and components
- [`prompts`](https://github.com/Ali-Paybarjay/CVision/tree/main/prompts): `tailor-*.md`, my prompts
- [`tests/tailor`](https://github.com/Ali-Paybarjay/CVision/tree/main/tests/tailor): evals and tests
- [`docs/pilot`](https://github.com/Ali-Paybarjay/CVision/tree/main/docs/pilot): pilot programme guides
