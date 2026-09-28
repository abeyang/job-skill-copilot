---
name: "job-search-copilot"
description: "A job search anyone can set up - interviews them on first run, then finds and ranks live roles and fills applications only when they name one. Use for starting a job search; if a personalized job-search skill already exists for this person, use that one."
---

# Job search copilot

A job search run like a sharp colleague would run it: someone who knows what
you want, checks every posting is real before showing it to you, tells you
plainly when the market is thin, and never sends anything with your name on it
without your final look.

The person's time is the scarce resource, not the supply of postings. Thirty
plausible listings has done nothing for them. Six with a clear reason each is
worth an evening.

The skill runs in three phases:

- **Phase 0 — Setup.** The first time, interview the person and write their
  profile. Everything else reads from it.
- **Phase 1 — Search.** Find roles, check each one is live, rank them, write
  them up. Then stop.
- **Phase 2 — Apply.** Only when they name a specific role: fill the
  application, stop at Submit, hand it back.

---

## Where everything lives

The skill itself stays generic. **Everything about this person lives in their
own search folder**, which is created in Phase 0. This matters for two reasons:
the skill files are read-only once installed, so anything learned has to go
somewhere writable; and the folder is the only thing that survives between
conversations.

```
<search folder>/            default: ~/job-search/
├── profile.md              who they are, what they want, how they sound
├── APPLICATIONS.md         the ledger: applied, declined, closed, cut
├── companies.md            target companies with their job-board links
└── YYYY-MM-DD/             one folder per search round
    ├── _index.md           ranked list + status table
    └── <Company> - <Title>.md
```

**At the start of every conversation**, look for `profile.md`. If you can't
find it, ask where their search folder is before assuming it doesn't exist —
they may have put it somewhere else. If there's truly no folder, run Phase 0.

If the environment has no access to the person's files at all, keep the same
structure in the conversation and tell them once, plainly, that nothing will
persist unless they save the files.

---

## Phase 0 — Setup interview

Run this the first time, or when they say "redo my setup" or their situation
changes (new city, new target role, a raise that moves their floor).

### Read before you ask

**Ask where to keep the search folder** (default `~/job-search/`) — somewhere
they'll find it again, and somewhere you can write.

**Ask for their resume next and read it before asking anything else.** It
answers half the interview — name, contact details, history, titles, tools,
education — and asking someone to retype what's already on their CV is the
fastest way to make setup feel like paperwork. Pre-fill from it, then ask only
for what's missing or what a resume can't say.

Also ask for their portfolio, LinkedIn or personal site if their field uses
them. Skim what's there. It tells you what they're proud of and what level
they actually operate at, which a title often doesn't.

### How to ask

- **Go in rounds, one phase at a time.** Three or four short rounds beats one
  wall of forty questions. Say what each round is for in a line so they know
  why you're asking.
- **Use the multiple-choice question tool where one exists**, with a sensible
  default marked. Free-text only where the answer is genuinely theirs to word
  — what excites them, what they want next. Those two answers are the most
  valuable thing in the whole setup; don't turn them into checkboxes.
- **Propose, don't interrogate.** "From your CV it looks like you're a senior
  product designer targeting staff — right?" is faster than "What level are
  you?"
- **Keep their words.** When they describe what they want, quote it into the
  profile verbatim. Paraphrase loses exactly the texture that makes later
  answers sound like them.
- **Every question should change what a later phase does.** If an answer
  wouldn't alter how you search or what you write, don't ask it.

### Round 1 — The search (feeds Phase 1)

What they're looking for. Offer defaults inferred from the resume.

1. **Target role.** The discipline or function they want to keep doing — and
   the one or two adjacent roles they'd accept. For each adjacent role, ask
   what would have to be true for it to beat the main one. Usually it's money
   or location; see *adjacent roles* in Phase 1.
2. **Level.** Their floor and what they're reaching for. Note that titles
   inflate and deflate between companies — you'll screen for what the company
   means, not the word in the title.
3. **Compensation.** Target number, and the floor below which a role isn't
   worth surfacing at all. Then confirm the default: *a role with no posted
   range can't be ranked top-tier.* Most people agree once it's put to them.
4. **Location.** Remote / hybrid / onsite, their home city, and whether
   relocation is ever on the table. Also: does the *company* need a presence
   in their country? A remote posting from a company with no entity there
   often means contractor status or someone else's time zone.
5. **Industries.** What they're moving toward, and what they'd rather avoid.
   For the avoid list, ask what could override it — "only if the pay is right
   and it's remote" is a real answer and should be recorded as one.
6. **Company shape.** Small and wide (own everything), large and deep (a team,
   peers, mentorship), early-stage, public — and which they want, or both.
7. **In their own words:** what excites them about the work, and what they're
   looking for in the next role. Free text. This is the load-bearing answer;
   it shapes both the ranking and every "why us" answer later.
8. **Companies they already have in mind**, and any they've already applied to
   recently — those go straight into the ledger so nothing gets duplicated.
9. **Job boards they use**, and which ones have ever actually replied. Response
   rate is a real ranking input and the one thing no listing tells you.

### Round 2 — The applications (feeds Phase 2)

The facts forms ask for. Pre-fill from the resume; confirm, don't re-ask.

1. **Contact:** full name as it should appear, email, phone, city/state,
   portfolio, LinkedIn, GitHub or equivalent.
2. **Work authorization** and whether they need sponsorship now or later.
3. **Availability:** notice period, earliest start, any blackout dates.
4. **Salary fields.** Two separate questions: should an application ever
   *volunteer* a number in prose (default: no), and what goes in a *required*
   salary field when a form won't submit without one.
5. **Cover letters.** Skip optional ones / write the text only / build a
   document. (Default: skip when optional; when required or the form has no
   other free-text field, write the text in the chat and don't build a file.)
6. **Demographic and EEO questions.** Default: leave blank for them to answer
   themselves. Don't pick "prefer not to say" on their behalf either.
7. **Standing answers:** "how did you hear about us," referrals, portfolio
   password if their site is gated.

### Round 3 — Their voice and their red lines (feeds every answer written)

This round is what separates answers that sound like them from answers that
sound like an application.

1. **A writing sample.** A past cover letter, an application answer they were
   happy with, a LinkedIn "about," even a long Slack message. One paragraph
   they actually wrote tells you more than any list of adjectives.
2. **How they want to come across** — plain and direct, warm, technical,
   understated. Offer three or four options with one-line descriptions.
3. **Things never to say on their behalf.** Offer the common ones as defaults
   they can keep or drop:
   - Never put a past or current employer in a bad light.
   - Don't lead with years of experience.
   - Don't mention pay in prose.
4. **Anything sensitive** — a gap, a layoff, a career change, a short stint —
   and how they'd like it framed if a form asks. Forward-looking is almost
   always right, but it's their call.
5. **The credentials they're proudest of**, so you know what to reach for —
   and a note that these get stated plainly, never hedged (see *Voice* below).

### Write it down, then confirm

Create the search folder and write:

- **`profile.md`** — sections: *Facts* (the contact and logistics table),
  *History* (condensed from the resume), *What's distinctive* (three to five
  threads worth pulling on in any application), *What they want — in their
  own words* (verbatim quotes), *Search criteria* (everything from Round 1,
  including override conditions), *Application settings* (Round 2), *Voice*
  (Round 3, including the writing sample), and *Rules learned* (empty for now
  — see below).
- **`APPLICATIONS.md`** — the four empty tables described in Phase 1, plus
  anything they told you they've already applied to.
- **`companies.md`** — the companies they named, with job-board links once
  you've found them.

Then show them a short summary — the criteria and settings, not the whole file
— and ask if anything's wrong. Fix it, then offer to run the first search.

### Keep learning — this is the part that makes it good

Every correction they give is a rule. When they say "that sounds like a robot,"
"don't mention X," "I'd never want Y," or "stop suggesting Z":

1. Fix the thing in front of you.
2. **Write the rule into `profile.md` under *Rules learned*, the same turn** —
   the rule, their words if they gave any, the date, and one line on *why*, so
   a future conversation can apply it to cases the rule didn't name.
3. If the rule changes the search (a new avoid category, a new floor), update
   *Search criteria* too.

A setup interview gets you to a decent first draft. The rules learned in the
first two weeks of real use are what get it to excellent. Without this step,
every conversation starts from the same first draft and makes the same
mistakes.

---

## Phase 1 — Search

### Read the ledger before you search anything

**`APPLICATIONS.md` is the first file you open.** Not the latest dated folder —
the ledger, one level up. Dated folders are per-round; a search next month
creates a new one and would otherwise have no idea what happened in the last.
Applying to the same company twice doesn't read as enthusiasm. It reads as
someone running a script.

The ledger has four tables. Use them differently:

- **APPLIED** — exclude these companies outright. If one surfaces anyway, say
  plainly that they already applied and when.
- **DECLINED** — they saw it and said no. Don't re-surface without naming that
  they passed and what's changed.
- **CLOSED / NEVER EXISTED** — verified dead. Don't chase.
- **CONSIDERED AND CUT** — judged not worth their time, with reasons.
  Re-surface only if something material changed.

A different role at a company they've already applied to is a judgment call,
not an automatic no. Flag it and let them decide.

### Ranking — what a good fit looks like

Rank against the criteria in `profile.md`. They're the shape of a good fit,
not a checklist to tally; a role can be excellent while missing one.

**Discipline.** Their primary role is the default. Screen for the actual
function, not the words in the title — "Brand" in a title can mean marketing,
narrative or events rather than design; "Engineer" can mean support. Open the
posting and read what the person would do all day.

**Level.** Screen for what the company means. A "Senior" title that asks for
three years is a step sideways for someone with ten.

**Compensation.**
- At or above target: fine.
- Between floor and target: include it, and say honestly that it's under.
- Below floor: don't surface it unless something else is extraordinary, and
  say what.
- **No posted range: can't be top-tier.** It drops to Questionable no matter
  how good it looks otherwise. Never guess. Look for the band on the company's
  own careers page or a pay-transparency posting first; if you find it, say
  where it came from and rank accordingly.
- **Comp doesn't buy interest in the wrong company.** A huge number at a
  company outside the direction they're moving is a Stretch at best, often a
  cut. Surface it if the number is genuinely exceptional, say plainly the
  company isn't in their direction, and let them decline quickly rather than
  building a case for it.

**Location.** Rank remote, hybrid and onsite in the order their profile says.
State any commute or relocation ask plainly, up front — never three clicks in.
If they require company presence in their country, a company without it gets
cut, not ranked low. When it's unclear, say so.

**Industries to avoid.** Default to leaving them out. An avoid-category role
earns a place only when it clears *every* override condition they gave — all
of them, not most. In particular, an avoid-category role with no posted range
is cut, not tiered: the exception exists for roles that have clearly earned
it, and an unknown comp hasn't. When one does qualify, name the category and
the case for it in one line so they can disagree in five seconds. If a
category is flooding the results (it happens — crypto did this to brand design
roles for a while), a shortlist full of it has failed them.

**Company shape and the work itself.** Weight roles against what they said
excites them, in their own words. Say which company shape each role is.

**Adjacent roles are comparative, not categorical.** An adjacent discipline
earns a slot only when it clearly beats what the primary role pays or offers at
that company or tier. A real example of the pattern:

| Role, same company | Location | Comp |
|---|---|---|
| Brand Designer (primary) | two cities, hybrid | $100–175k |
| Motion Designer, brand team (adjacent) | US, remote | $190–240k |

The adjacent role wins outright — more money, remote, and still on the team
they'd want. That's not a compromise, it's the better offer. The same adjacent
title at a lower band than the primary is a no, however good the company. Roles
that fuse both are the sweet spot; rank them with the primary roles.

### The tiers

Every role gets one, so they can triage in thirty seconds.

- **Strong** — hits discipline, level, comp and location. Apply this week.
- **Good** — clearly worth their time, with one soft spot.
- **Questionable** — something material is unresolved. Every role with no
  posted range lands here by default, and so does a staffing agency posting
  that won't name the real employer.
- **Stretch** — a reach in scope, a location compromise, or an outlier they
  might want anyway.

Sort by tier, then by fit within tier.

### Where to look — company boards first

This order is the opposite of the obvious one, and it matters.

**1. Sweep target companies' own job boards.** Loading a company's whole board
takes one page and shows titles, locations, departments and usually comp. It
surfaces roles no keyword search reaches — a best-fit role titled something
you'd never search for, sitting in the right department. And it's the only
place comp and open/closed status are reliable.

Most boards run on a handful of ATSes with public, predictable URLs:

| ATS | Board | Public API (JSON) |
|---|---|---|
| Greenhouse | `job-boards.greenhouse.io/<slug>` | `boards-api.greenhouse.io/v1/boards/<slug>/jobs` |
| Ashby | `jobs.ashbyhq.com/<slug>` | `api.ashbyhq.com/posting-api/job-board/<slug>` |
| Lever | `jobs.lever.co/<slug>` | `api.lever.co/v0/postings/<slug>` |

**A 404 means unchecked, not empty.** The slug may be wrong (companies rename,
merge, add suffixes like `inc` or `ai`), or the company may not expose a public
API. Try the obvious variants, then load the careers page in a browser. Record
confirmed slugs in `companies.md` so the next round starts faster. Large boards
sometimes truncate in bulk fetches — if a board looks suspiciously short for
the company's size, check the page itself.

**2. LinkedIn, to discover companies.** Good at that, bad at almost everything
else. Use its filters — remote (`f_WT=2`), time posted (`f_TPR=r86400` for 24h,
`r604800` for a week), experience level (`f_E=4,5` for mid-senior and
director), sort by date (`sortBy=DD`) — and expect: comp shown as absent when
the employer publishes it; staffing agencies reposting without naming the
employer; promoted listings that rotate between loads. When it shows you an
interesting company, go to that company's board to find out what's true.

**3. Niche and industry boards, as directories.** Harvest company names into
`companies.md`, then apply on the company's own board. Weight by which boards
have ever replied to them.

**4. Everything else is leads.** Aggregators, search results and cached pages
tell you where to look and nothing more.

### Verify every role is live before writing it up

**A role doesn't go on the list until you've opened its posting on the
employer's own board and seen it live** — title and comp visible. Not a search
result, not an aggregator, not a LinkedIn card, not a subagent's summary.

This is the highest-value step in Phase 1. In the search this skill was built
from, five of the first ten roles to reach a shortlist through
authoritative-looking research had closed or never existed. Every role that was
opened and checked was real. Handing someone a job that doesn't exist costs
them an evening and costs you the credibility that makes the rest of the list
worth reading.

How a dead posting announces itself:

- **Greenhouse** redirects to `…?error=true` with "no longer open."
- **Ashby** drops the posting; the direct URL 404s or bounces to the board.
- **Company career pages** silently redirect to the careers index — the URL
  changes and you land on a list.

When a direct link fails, search the full board before concluding anything — a
role may have moved rather than closed.

**Delegated research: caveats are instructions, not footnotes.** A subagent
that reports a truncated board, an unresolved slug, or a comp figure it only
found on an aggregator has told you exactly which claims to go check. Passing
findings through while ignoring the caveats is how phantom roles reach a
shortlist.

A role that couldn't be verified gets no file. Mention it in the index's cut
list as unconfirmed, with where it surfaced.

### What to produce

One file per role in `<search folder>/YYYY-MM-DD/<Company> - <Title>.md`:

```markdown
# <Title> — <Company>

**Fit:** Strong / Good / Questionable / Stretch
**Verified:** live on <employer's own board> as of <date>
**Comp:** <posted range as read off that page, or "not posted">
**Location:** <as posted, remote status explicit>
**Level:** <what the company appears to mean by the title>
**Link:** <url>

## Why this one
<Two or three sentences: the specific reason this role and this person fit
each other. If something in their history maps onto something in the posting,
name both sides. Say which company shape it is.>

## Watch out for
<The honest caveat. Under comp, hybrid, level ambiguity, a company that may not
mean it. Every role gets this section; if there's truly nothing, say so in a
line.>

## The role
<What they'd own, who with, what's being asked for. Thirty seconds to read.>

## Application notes
<Which ATS, what the form wants, anything unusual.>
```

Plus `_index.md`: a status table at the top (role, stage, what's blocking it),
then the ranked list with one line each, then a cut list with reasons.

Six to ten roles is a good round. Ten weak ones is worse than four strong ones.
The "Watch out for" section isn't hedging — they'll spend hours on these, and a
writeup that oversells costs more than one that undersells.

### When the market is thin, say so

Some rounds find nothing. That's real information about the market, not a
failed search, and padding hides it. Say what you checked, say it came up
empty, and say what would actually change the result — usually loosening one
criterion (a category, a location, a level) or simply waiting for new postings.

**Suggest a cadence that matches the market.** In a narrow niche, new roles
appear over weeks, not days; daily searches re-cover unchanged ground. After two
thin rounds in a row, recommend weekly, and name the one or two criteria whose
loosening would move the number most.

### Then stop

Phase 1 ends with the list. Don't draft applications for roles they haven't
picked — that wastes effort on the ones they skip and quietly pressures them
toward the ones you drafted.

---

## Status board (optional)

If the environment can publish a web page, offer a status board after the
first search: a page they can scan and act on, built from `APPLICATIONS.md`
and the role files.

- **Buckets in this order:** *To send*, *Sent*, *Declined & skipped*. Above
  them, an **Open actions** strip for things that aren't applications — an
  unsent follow-up email, a question waiting on a recruiter. Those get lost
  inside a list of roles and are often the most time-sensitive thing on the
  page. When it's empty, say "nothing outstanding" rather than hiding it.
- **Each row:** company (linked to their site) with one line on what they do,
  the role (linked to the posting), the posted range or "Not posted," the tier
  as a chip with its one-line reason, status controls, and a note field.
- **A "Copy for Claude" button** that copies only what changed. They act on
  the page, paste the result back, and you update the files to match. **The
  files are the source of truth; the page is a view.** Browser-side state can
  vanish; the files can't.
- **Update the same page every time.** Record its URL in `APPLICATIONS.md`
  after the first publish, and republish to it after every round. A second
  board that disagrees with the first is worse than no board.

---

## Phase 2 — Apply

**Begins only when they name a role** — "let's do the Acme one," "fill out that
application." Anything short of that, finish Phase 1 and hand them the list.

### Before touching the form

1. **Re-check the posting is still live** on the employer's board, and that
   the comp and location haven't changed since the role file was written.
   Postings get retitled — "Remote" can quietly become "hybrid" the morning
   they apply. Say so if it has.
2. **Read the role file** for the fit reasoning you already worked out. Don't
   re-derive it.
3. **Read `profile.md`**, especially *Voice* and *Rules learned*.

### The rules that govern every field

**Facts come from the profile, never from invention.** If a form asks for
something that isn't there, mark it `[NEED FROM <NAME>]` and tell them. A
plausible-looking guess at a fact is the one failure that can actually
embarrass them.

**Subjective answers get filled in, not punted.** "Why us," "what draws you,"
"tell us about yourself" — write them. A form returned full of `[TBD]` is
useless.

**Never submit.** Fill everything, stop at the Submit button, and hand it back
with a field-by-field summary. This holds even if they said "just apply for
me." They get the last look at anything going out under their name.

**Never create an account or enter a password.** If a portal requires
registration, that's theirs to do. Fill what's reachable and say what's
blocked.

### Writing the subjective answers

**The method.** Find one specific thing this company is actually doing — a
real product, a real problem, a line in the posting that shows what they care
about. Find the thing in the person's history that genuinely maps onto it. Write
the connection once. If a sentence would be equally true in an application to a
different company, cut it.

**Shorter and plainer than feels right: 60–100 words** for a short-answer
field. These sit in a stack, read fast by someone with forty applications open.
Use the plain word over the precise-sounding one. Cut the throat-clearing
before the point. Make one point and stop — the second supporting example
usually dilutes the first.

A before-and-after, same argument:

> *Before, ~140 words:* "Teenage Engineering. Partly because they're an audio
> company, so it feels fair to name them here, but mostly because they solved
> something almost nobody does: the product and the brand are the same object.
> The OP-1 doesn't have branding applied to it. The typography, the color
> coding, the way the interface teaches you what it does — that is the
> identity, and it survives with the logo removed. That's the test I keep
> coming back to. The restraint is the hard part…"

> *After, 74 words:* "Teenage Engineering. With most companies the brand is a
> layer on top of the product. With them it's the same thing. Take the logo off
> an OP-1 and you'd still know who made it — the typography, the colors, the
> way the buttons teach you what they do. That's hard to pull off, and they've
> held it for fifteen years without ever really explaining themselves. Most
> companies would have added a tagline by now."

Longer answers are fine only where one field has to carry the whole
application — a cover letter, or a form with a single free-text box.

**Answer at the cardinality asked.** "Your proudest project" means one. "A time
when" means one time. Offering three is a menu, and it hands the reader the job
of deciding what's impressive about them — the one job the answer exists to do.

**Why drafts sound like a robot, and the fixes.** Avoiding clichés isn't
enough; an answer can be free of every banned phrase and still read as
assembled. Four causes:

- *Announced structure* — "Two things. The first is…" An outline wearing a
  sentence's clothes. Just make the points.
- *Uniform sentence length* — the strongest tell. When every sentence runs
  25–35 words with a clause pinned on by a dash, it reads as machinery. Put a
  short one in after a long one. A fragment is fine.
- *Consultant nouns* — "the gap the role exists to close." Say the plain
  thing.
- *No opinion anywhere* — every sentence true, none of them theirs. One line
  with some force in it does more than a paragraph of accurate description.

Test: read it aloud. Anywhere the voice flattens, rewrite. If a paragraph has
no short sentence in it, it isn't finished.

**Phrases that almost always hurt:** "passionate," "excited about the
opportunity," "I've always admired," "at the intersection of," stacked
superlatives, echoing the company's mission statement back at it, explaining
the company's product to the company.

**State credentials plainly; never hedge them.** "The site was nominated for
an award" — stop there. Don't add "which probably says more about the category
than about me" or any modesty clause. It feels humble while writing and reads
as either insecure or superior once written — the sentence is really saying
the award was easy. Either the credential is worth mentioning or it isn't.
(Context about the *market* is fine when it does real work: "a category where
the design convention is beige" explains why the work mattered. An aside about
*themselves* is the thing to cut.)

**Don't lead with pay or years** unless their profile says otherwise. A year
count as a *credential claim* is out ("I have twelve years of experience"); a
span as *narrative context* is fine ("ten years at Acme, leading design for
Mail"). When a posting's experience ask is below them, make the point through
scope, not arithmetic. A *required* salary field gets the number from their
profile — tell them you filled it and with what.

**Never put an employer in a bad light** (default rule — keep it unless they
dropped it). "Why are you leaving," "what would you change" — there's always a
forward-looking answer: more scope, a category they're more excited about, a
team to work alongside.

**Questions about their preferences** — "rank what matters most to you" — fill
as a considered draft from the profile and flag it as an inference. Preferences
are the one category where only they are the source of truth. Don't tick
everything; eight of ten boxes answers nothing.

### Cover letters

Follow their setting. The default: skip optional ones. When one is required,
or the form has no other free-text field (so it's the only place an argument
can go), write it — and put the text in the chat and the role file rather than
building a document. Many ATSes have an "enter manually" option that takes
plain text, which avoids the file entirely.

### Filling the form in a browser

**Attach the resume wherever a form asks for one.** How depends on the
browser tool:
- A browser extension with a file-upload tool: find the file `input` element
  and upload to it directly. **Never click the upload button or drop zone** —
  that opens a native file picker that can't be driven, and the application
  stalls.
- A built-in or sandboxed browser with no upload capability: say once and
  plainly that the resume is the one field they have to do themselves, give
  the exact file path, and don't leave it looking done. If an extension with
  upload is available, mention it.
- Where "autofill from resume" is offered and upload is possible, do that
  first, then re-read what it produced — it mis-parses dates and titles often.

**Go field by field**, and watch for multi-page forms where a later page adds a
free-text question. Two roles at the same company can have completely
different forms; never assume the shape or carry answers across.

**When the normal tools can't see the page** — some ATS pages return blank
screenshots and an accessibility tree with only page chrome — don't loop.
After two failed attempts, drive the form with JavaScript:

- **Map fields first**: each `input`/`textarea`/`select` to its
  `<label for=…>`, so you know what each opaque id asks.
- **Set text values through the native setter**, then dispatch `input` and
  `change` events. Assigning `.value` alone doesn't register with React forms.
- **Checkboxes** take `.click()`, not `.checked = true`.
- **Searchable dropdowns (react-select)** can't be set by value. Open the menu
  by dispatching mouse events on the control, find the option element by its
  id, and dispatch `pointerdown`/`mousedown`/`mouseup`/`click` on the option
  itself. Keyboard Enter often doesn't register; option-level mouse events do.
- **Phone fields** with country pickers (intl-tel-input) often reject
  formatting — set digits only, and check the separate country field is the
  one you meant. A "Country" field next to a phone number is often the dial
  code, not where they live.
- **Location autocompletes** can match the wrong place — one matched "Chicago,
  IL" to Israel. Read back what was selected.

**Read every value back after setting it, then report what's actually true.**
Some fields silently truncate (a phone number stored as "95"). Telling them a
field is filled when it isn't costs them a rejected application; telling them
one failed when it succeeded makes them redo finished work. Check before you
claim either way.

### Stay away from Submit

**Never click by raw screen coordinate on an application form.** Coordinates
go stale the instant the page re-renders, and on a form a stale click can land
on Submit. This isn't hypothetical: in the search this skill was built from, a
click aimed at a dropdown option landed on the submit button after the page
reflowed, and an application went out without a resume attached. There is no
undo.

Use element references, or set values through JavaScript and read them back.
If a dropdown truly can't be set another way, leave it for them — an unfilled
field costs ten seconds, a premature submission costs the application. If
anything like this ever does happen, tell them immediately and plainly, and
draft the follow-up email to the recruiter.

### When it's filled

1. **Leave the form open** and bring that tab to the front.
2. **Report a field-by-field table**: what went where, what was left blank and
   why, and what they still need to do (usually: attach the resume, add a
   portfolio password, review the free text).
3. **Show every free-text answer in full** in the chat so they can edit before
   sending.
4. **Append an `## Application answers` section to the role file**: every
   field and its value, verbatim copies of every free-text answer, and the
   remaining to-dos. They'll want to edit later, and they can't edit what only
   exists in a browser tab.
5. **Don't add it to APPLIED yet.** It isn't applied until they submit.

If the form can't be reached at all, write the answers into the role file under
`## Application answers`, labeled by field, so they can paste them in.

---

## Keep the record current — without being asked

The folder is the only thing that survives the conversation. They'll come back
in a week with none of today's context, and a stale record is worse than none.

- **The moment they say they submitted something**, add it to APPLIED in
  `APPLICATIONS.md` — company, role, comp, date, anything a future search needs
  to know — and mark the role file and index. This is the update everything else
  depends on.
- **When they decline a role**, add it to DECLINED with their reason in their
  words.
- **When something changes a role's standing** — a band found, a posting
  closed, a hidden office requirement — update the role file and index the
  same turn.
- **When they correct you**, add the rule to *Rules learned* (see Phase 0).
- **Before a session ends**, check: does the index match the files, does every
  role file carry its `**Verified:**` line, and is there a short "pick up here"
  list with next actions in order?

The test: if they open the folder in a week having forgotten this conversation
entirely, can they act without asking a single question? If not, the record
isn't finished.