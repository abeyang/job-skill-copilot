# Job Search Copilot

A Claude skill that runs your job search like a sharp colleague would. It learns
what you want, checks that every posting is real before showing it to you,
ranks roles honestly, and fills out applications — but never submits one. You
always get the last look.

---

## What it does

It works in three phases, and it only moves from one to the next when you say so.

| Phase | What happens | How you start it |
|---|---|---|
| **0 — Setup** | A short interview about what you're looking for. It runs once and saves your answers. | Runs automatically the first time |
| **1 — Search** | Finds roles, checks each one is still open on the company's own site, ranks them, and writes each one up. Then it stops. | *"Find me jobs"* · *"Run a search"* |
| **2 — Apply** | Fills out the application for a role you pick, stops before Submit, and shows you everything it entered. | *"Fill out the Acme application"* |

The search never turns into applications on its own. You pick the role; it
does the form.

---

## Install

1. Download `job-search-copilot.skill`.
2. In Claude, go to **Customize → Skills** and upload the file. You can also
   drop it into a chat and ask Claude to install it.
3. Start a new conversation and say something like *"help me find a new job."*

**Works best in Cowork** (the Claude desktop app) with a folder on your computer
connected, so it can save your files between conversations. It also needs a
browser to fill out applications (see *Browser setup* below).

---

## Your first run

Have these ready. It takes about ten minutes.

- **Your resume** (PDF or Word). It reads this first so it doesn't ask you for
  things that are already on it.
- **Your portfolio, LinkedIn, or personal site**, if your field uses them.
- **One paragraph you've written yourself** — an old cover letter, a LinkedIn
  "about" section, even a long Slack message. It uses this to make answers
  sound like you.

It then asks three short rounds of questions:

1. **The search** — what role you want, your level, your pay target and floor,
   remote or in-office, industries you're moving toward or avoiding (and what
   would change your mind), company size, and — in your own words — what
   excites you about the work.
2. **The applications** — contact details, work authorization, notice period,
   how to handle salary fields, and whether to write cover letters.
3. **Your voice** — how you want to come across, anything it should never say
   for you, and how to frame anything sensitive like a gap or a layoff.

The two free-text answers about what excites you and what you want next matter
most. Take a minute on them.

---

## Where your files go

Everything about you lives in one folder that you choose (the default is
`~/job-search/`). The skill itself stays generic.

```
job-search/
├── profile.md          who you are, what you want, how you sound
├── APPLICATIONS.md     every place you've applied, declined, or ruled out
├── companies.md        target companies and their job-board links
└── 2026-09-28/         one folder per search
    ├── _index.md       ranked shortlist + what's blocking each role
    └── Acme - Senior Designer.md
```

**`APPLICATIONS.md` is the important one.** Every search reads it first, so you
never get sent back to a company you've already applied to. When you submit
something, tell Claude so it can record it.

---

## How roles get ranked

Every role gets one of four tiers:

- **Strong** — fits on role, level, pay, and location. Apply this week.
- **Good** — worth your time, with one weak spot.
- **Questionable** — something important is unknown. **A role with no posted
  pay range always lands here**, however good it looks.
- **Stretch** — a reach, a location compromise, or an outlier.

Each writeup includes a **"Watch out for"** section with the honest downside.
If the market is thin that week, it says so rather than padding the list.

---

## What it will never do

- **Submit an application.** It fills everything, stops at Submit, and hands it
  back to you.
- **Show you a job it hasn't checked.** Every role is confirmed live on the
  employer's own job board first. Job aggregators and search results are
  treated as leads, not facts.
- **Make up a fact.** If a form asks for something it doesn't know, it marks the
  field and asks you.
- **Create accounts or enter passwords.**
- **Mention your salary or years of experience in written answers**, or say
  anything negative about a past employer — unless you tell it otherwise.

---

## Browser setup

To fill out applications, Claude needs a browser.

- **Claude in Chrome (the extension)** — recommended. It can attach your resume
  automatically.
- **Claude's built-in browser** — works, but it can't upload files, so you'll
  attach the resume yourself. It will tell you which file.

Either way, it leaves the form open for you to review and submit.

---

## Tips

- **Correct it.** When something sounds off — *"too long," "that's not how I'd
  say it," "stop showing me X"* — say so. It saves each correction to your
  profile as a rule, and gets noticeably better within a week or two.
- **Search weekly, not daily.** In a narrow field, new roles show up over weeks.
  After a couple of thin rounds, it will suggest slowing down and point to the
  one criterion that would open things up most.
- **Ask for `status`** after a search to get a one-page board of what's queued,
  sent, and declined — if your Claude setup can publish pages.
- **Redo your setup** whenever your situation changes: *"redo my job search
  setup."*

---

## Limitations

- It can only check company job boards that are publicly reachable. Some
  companies hide theirs behind login pages or custom sites, and those need a
  manual look.
- Sites like LinkedIn may need you to be signed in within the browser Claude is
  using.
- It drafts written answers, but you're the final editor. Read everything
  before you submit.
