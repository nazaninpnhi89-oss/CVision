# CVision

**Every application, made to fit.**

> This is Nazanin's fork of the team repository [Ali-Paybarjay/CVision](https://github.com/Ali-Paybarjay/CVision), shared as a portfolio project. **My part of the work: [CONTRIBUTION.md](CONTRIBUTION.md)**

## About (English)

CVision is a job-application tailoring app for the UK. Upload your CV, paste a job ad, and get a CV and cover letter tailored to that ad. Paste. Tailor. Apply.

- **Live app:** https://cvision-eta.vercel.app
- **Team repository:** https://github.com/Ali-Paybarjay/CVision

### What it does

- **Free 2-minute CV check:** quick feedback on a CV, no account needed.
- **Profile and match:** reads your CV into a Profile, asks follow-up questions, reads the job ad and shows how well you match it.
- **Tailored CV and cover letter:** asks about the gaps between your CV and the job, suggests changes you approve one by one, and writes a cover letter you can edit paragraph by paragraph.
- **Export and Apply:** download as PDF or Word, and keep every version you send.
- **Interview practice:** practise questions for the same job and get feedback.
- **Tracker and your data:** track your applications, download all your data, or delete it.

### The Honest CV Promise

CVision never adds a skill or experience you have not given evidence for, never applies a change without your approval, and never applies for a job on your behalf. You can download and fully delete your data.

### Tech stack

Next.js 16, React 19, TypeScript, Zod contracts, Supabase (Postgres with row-level security), the Claude API, Vitest, Playwright, GitHub Actions and Vercel.

### Team

Built by a team of four, each owning one part of the app:

| Name | GitHub | Part of the app |
|---|---|---|
| Ali Paybarjay | [Ali-Paybarjay](https://github.com/Ali-Paybarjay) | Tech lead: foundation, brand, dashboard, database and deploys |
| Shayan | [shsheytan](https://github.com/shsheytan) | CV upload, Profile and job matching; quality and testing |
| Nazanin | [nazaninpnhi89-oss](https://github.com/nazaninpnhi89-oss) | Tailored CV and cover letter, export and Apply; pilot programme |
| Marzieh | [Marzieh-Manager](https://github.com/Marzieh-Manager) | CV check and interview practice; product and pitch |

### A note on language

The team worked in Persian, so issues, pull requests and commit messages are in Persian. The code, prompts and everything in the app are in UK English.

### Run it locally

```bash
npm install
npm run dev
```

Open http://localhost:3000. By default the app runs in mock mode (`AI_MODE=mock`), so no API key is needed. To use the real model and the database, create `.env.local` from `.env.example`.

---

## فارسی

اپ تنظیم درخواست شغلی برای بریتانیا: کاربر رزومه‌اش را آپلود می‌کند، آگهی را می‌چسباند و رزومه و کاورلتر اختصاصی همان آگهی را می‌گیرد. Paste. Tailor. Apply.

- **نسخهٔ آنلاین:** https://cvision-eta.vercel.app
- **برد کارهای تیم:** https://github.com/users/Ali-Paybarjay/projects/1 (اول راهنمای تیم را که در بالای برد لینک شده بخوان)

## اجرا روی کامپیوتر خودت

```bash
npm install
npm run dev
```

بعد http://localhost:3000 را باز کن. فایل `.env.local` را طبق `.env.example` و راهنمای تیم بساز.

## کار روی پروژه

- قواعد تیم، صاحب هر پوشه و زبان کار: [CLAUDE.md](CLAUDE.md). این فایل برای Claude Code به انگلیسی است و Claude Code هر نفر خودش آن را می‌خواند.
- برند گاید: [docs/brand.md](docs/brand.md)
- زبان: هر چه در GitHub می‌نویسیم فارسی است؛ کد، اسم فایل‌ها و شاخه‌ها و متن‌های اپ انگلیسی‌اند.

CVision نام موقت است.
