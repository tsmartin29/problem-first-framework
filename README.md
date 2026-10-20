# Problem-first: build only what solves a real, sourced pain

A working method for a small software team (or one person with AI coding sessions): start from a pain someone actually reported, decide what "solved" means before you build, and measure it against something independent.

Made by Tommy Martin. Built while running [ClubPlugins](https://clubplugins.com).

**Honest status.** This is the method we settled on after getting it wrong a few times: building features nobody asked for, writing marketing about problems nobody had, grading ourselves against a competitor's output, and calling things "done" that failed on first use. It is one small company's practice, not a proven framework. It is written for people who build tools for a specific community (we build for DJs and music producers), and the examples come from that. Everything here uses public facts only. If you also run a lot of AI sessions, the companion guide is [solo-company-claude-playbook](https://github.com/tsmartin29/solo-company-claude-playbook); this guide does not repeat it.

## Contents

1. [The rule in one paragraph](#1-the-rule-in-one-paragraph)
2. [Start from a sourced pain](#2-start-from-a-sourced-pain)
3. [The pain map](#3-the-pain-map)
4. [Never invent problems](#4-never-invent-problems)
5. [Choosing what to build](#5-choosing-what-to-build)
6. [Define "solved" before you build](#6-define-solved-before-you-build)
7. [Measure against independent truth](#7-measure-against-independent-truth)
8. [Fewest options](#8-fewest-options)
9. [The hands-on test is the gate](#9-the-hands-on-test-is-the-gate)
10. [Copy: facts and the pain solved](#10-copy-facts-and-the-pain-solved)
11. [Judge sales on full cohorts](#11-judge-sales-on-full-cohorts)
12. [Watch competitors before you plan or claim](#12-watch-competitors-before-you-plan-or-claim)
13. [Kill or keep](#13-kill-or-keep)
14. [Worked examples](#14-worked-examples)
15. [Templates and starter checklist](#15-templates-and-starter-checklist)

## 1. The rule in one paragraph

Every feature, plan, price change and sentence of marketing should trace to a pain that a real person reported, with the quote and the link kept. If you cannot point to the source, either go and find one or do not build it. Before building, write down a test that says what "solved" means. After building, run the test against an answer key that does not come from you or from a competitor, and let a real user try the result before it ships. Anything that fails any of those steps is not done.

## 2. Start from a sourced pain

Pains come from four kinds of place. Keep a record of which one each came from, because they are not equally strong.

- **Public forums and communities.** Subreddits, vendor forums, Discord archives, Gearspace-style boards. Strong when many people describe the same thing in their own words.
- **Reviews and support threads about existing tools.** App store reviews, Trustpilot, vendor changelogs with complaints underneath. Strong for "what do people leave a tool over".
- **Your own support emails and trial feedback.** The best evidence, and usually the scarcest at the start. When we searched our own records, there was almost no real customer text on file. Say so in the pain map rather than padding it.
- **The founder's own use.** Valid, because the founder is a user (ours is a working DJ and producer). Label it as such: "founder, from his own gigs" is a source, but it is one person.

Rules for collecting:

- **Keep the quote and the link.** Copy the sentence exactly, keep it short, and keep the URL and date. A pain without a quote is a rumour. (Mind copyright: short quotes only, never reproduce long passages.)
- **Count honestly.** If a search tool misses time windows or you can only match post titles, then your count is a lower bound. Write "at least 39 threads, title match only", not "39 threads".
- **Separate "how many people" from "how many threads".** Threads are not people. Write what you counted.
- **Record where you could not look.** "Not covered: these three communities" is part of the evidence.
- **Do not sign up, post or message people in order to research.** Read what is already public.

## 3. The pain map

One table (or file) that every plan points back to. One row per pain:

| Field | What goes in it |
|---|---|
| **Who** | The person, in their own role ("a DJ who plays from USB drives"), not a demographic. |
| **Pain** | What goes wrong, in their words. |
| **Evidence** | Quote, link, date. How many sources. Where you could not look. |
| **How often** | How many people hit it, and how often each person hits it (every gig, once a year). |
| **How badly** | What it costs them when it happens: minutes, a ruined set, lost data, money. |
| **What they use now** | The incumbent tool or the workaround, including doing it by hand. |
| **What it costs them** | Time, money, risk, or confidence. This is what you are competing with. |
| **Do we solve it?** | Solves / partly solves / does not solve, judged against a test, and "not tested yet" is a valid answer. |

Two habits made the map useful:

- **A "weak or missing evidence" list.** Things we assumed were pains but could not source go on a separate list and are not ranked. This stopped several plausible-sounding ideas from becoming plans.
- **An honest "do we solve it?" column.** The first honest pass of ours said "partly" for most rows, because we had not measured the hard cases. That was the useful result: it told us which test sets to build.

A template is in `templates/pain-map.md`.

## 4. Never invent problems

The most expensive mistake in our early copy was a small one. The founder gave us the real problems his product addresses. In drafting a public page, a session "improved" one of them with two extra symptoms that sounded plausible. They went live. The founder, who uses the product, said he had never experienced either. He was right, and a public page had put false experiences in a user's mouth.

Rules that came out of it:

- **Problem lines come only from the person's own words or from documented facts** (release notes, support threads, published bug reports). If in doubt, cite the source next to the draft.
- **A hypothetical third person is fine** ("a DJ whose USB fails in the club") but adds no extra symptoms.
- **Use the words your users use.** Our users say "USB", so the copy says "USB". Learn the vocabulary from the sources, and do not rename it.
- **Give the founder or owner a review pass for problem statements specifically**, since they are the person most likely to spot a made-up one.

## 5. Choosing what to build

Rank pains by three things, roughly multiplied:

1. **Severity.** What does it cost when it happens? A ruined set outranks a slow import.
2. **Frequency.** How many people, and how often each?
3. **How badly current tools fail.** If the incumbent already solves it well, a new tool needs a large advantage. If the incumbent's own users complain loudly and work around it by hand, there is room.

Then apply filters:

- **Does the evidence exist?** If not, the item goes to research, not to the roadmap.
- **Can you make it measurably better, not just different?** If you cannot describe the measurement, you cannot claim it (see section 6).
- **Is it reachable by the people you can reach?** A real pain in a group you cannot sell to is still not a plan.
- **Flag work that solves nobody's reported pain.** We run a standing check: "Which sourced pain does this trace to?" Items with no answer are marked, not silently built.

**Size by category, not by hope.** When we built sales projections, our first version gave every product the same assumed demand per channel, so the ranking followed launch order rather than real demand. Sizing each product from its own category (how crowded it is, what buyers already get free, how large the reachable group is) fixed it. A niche utility should not outrank a broad tool in your own model, and if it does, check the model first.

**Name the largest risk first.** Any plan or projection should open with the single biggest risk, and for us that was shipping something that does not impress its users. Tie it to evidence: how much hands-on testing the product has had, which failures are open, whether it has been tried in the real host application.

## 6. Define "solved" before you build

Write the test first. A good "solved when" is something another person could run and get the same answer.

- **Bad:** "Beat grids are better."
- **Better:** "On a published set of annotated tracks, including the hard cases people complained about (grid correct at the start but off after a breakdown; half-time material), the grid is within a stated tolerance on at least a stated share of tracks, and the result is published with the method."
- **Bad:** "USB export is reliable."
- **Better:** "After export, a built-in check confirms every track on the drive has a waveform, a grid and its cues, and the drive loads on named hardware models. Anything not tested on hardware is not claimed."

The brief is one page: the problem, the evidence, the "solved when" test, and the non-goals (what you will deliberately not do). A template is in `templates/problem-brief.md`.

Two things that kept the test honest:

- **Build the test set from the complaints.** Take the exact cases people described, not only convenient examples.
- **Decide the claim in advance.** The only sentence you will be allowed to publish is the one the test supports ("matches or beats X on this set"), not a stronger one.

## 7. Measure against independent truth

If you grade your output against another tool's output, you are only measuring agreement with that tool. The other tool might be wrong, and agreement would then count against you for being right.

- **Use an independent answer key:** human-annotated public data sets, a signal in the material itself (for audio, the track's own kick drum position), or synthetic cases with known truth.
- **Score everyone on the same key, including yourself and the incumbent.** The incumbent is a contestant, not the reference.
- **Ban "within X of the incumbent" as an accuracy statement.** It is a compatibility statement at most, and should be worded as one.
- **Test on data the model never saw.** For anything learned or tuned (we classify audio samples by what they sound like, with file names only as a small nudge), measure on groups of data held out completely, grouped by source, not on a random split of the training material.
- **Know when to keep a rule that looks wrong.** We let a tempo written in a file name stand over the measured tempo, because on our test the measurement overruled correct names more often than wrong ones. That choice came from measuring both, which is the point.
- **Let the audio (or the data) decide, with metadata as a hint.** Names, tags and folders are what people typed, which is not the same as what is true.

## 8. Fewest options

Default to simplicity. For anything unreleased, cut the number of controls as far as you can. A tool a person reaches for in the middle of their work should already know its job.

- Describe the single moment the product serves, and design backwards from it.
- Every option is a decision the user has to make and a reason to hesitate. Move optional things behind a sensible default, or leave them out.
- Simple does not mean timid. A focused, opinionated tool with a strong default beats a deep options panel.
- Shipped products are the exception: do not reopen them under this rule. Apply it to new design and to the roadmap.
- Fewer options also means fewer states to test, which makes your "solved" test cheaper.

## 9. The hands-on test is the gate

Passing automated tests is not the same as working. We had a stretch where many products were reported as built, tested and installed on the strength of unit tests and a validator, and then failed straight away for the founder: features that did nothing, windows that grew and would not shrink.

What changed:

- **Test the installed thing, as a user would.** Load it into the real host, resize, close and reopen, save and reload, try every control and every promised feature, and look at the rendered result.
- **A realistic session, not one action in a loop.** Stress loops are extra checks. They do not replace a walkthrough.
- **Say what was and was not tried by hand.** Honest reporting beats a green tick.
- **The builder does not grade the build.** Use a separate tester (or session).
- **Do not steal the person's screen.** Automated UI tests must not take focus or the keyboard.
- **The founder or the user tries it hands-on before it counts.** For our founder, using a plug-in directly in his own session was far more informative than a rendered before-and-after file. So the handoff is an installed build plus click-by-click steps to try it, not a bundle of A/B renders. Renders are fine for marketing, not for review.
- **Estimate in build time, and name the human test round as the gate.** We kept quoting developer-days for work that took a couple of hours, and the real time went into verification and the human trying it. Say "built tonight, ready for your test", not "about a week".
- **Freeze features before launch.** Pick a date after which only fixes go in.

## 10. Copy: facts and the pain solved

Marketing copy states what the thing does and which reported pain it addresses. It does not perform.

- **No slogans or clipped fragments.** Strings of two-to-five-word sentences ("Pick X. Do Y. Get Z.") read as fake. Write ordinary full sentences, or on a product page, plain fact lists and spec tables: names, formats, numbers, dates.
- **Every claim is backed by a test you ran.** Keep a claims ledger (`templates/claim-check.md`): the claim, the test, the date, the build it was run on, and whether the test is stale. A claim whose test predates a significant change is held until you re-run it.
- **Show the real product.** For software, a screenshot of the actual interface in every ad and card. A type-only ad sells an idea, not the product. Use real names in screenshots rather than placeholders.
- **Do not name rivals' products or show their interfaces** unless you have checked you may. Compare on your own measured numbers.
- **No "uncrackable", "fully secure" or similar** unless you can prove it.
- **Consistency checks before handoff:** numbers formatted one way everywhere, dates in one style, product names spelled one way.

## 11. Judge sales on full cohorts

If your product has a trial, sales lag downloads by the length of the trial. We were burned by applying an early rate to downloads whose trials had not ended and then reading the launch as failing on day three.

- **Judge on cohorts whose trial window has closed.** Group downloads by day and wait for each group to expire before you count outcomes.
- **Show trials ending per day, and the paid share of each finished cohort.** Do not project a month from three days of downloads.
- **Count only outside people.** Your own deploy checks, test installs and automatic updates can all register as downloads. Keep a ledger of your own downloads and subtract it, and never quote a raw counter as customers. The companion guide claude-business-launch (coming soon) covers download tracking in more detail.
- **Keep the readout short:** numbers and the next action. Do not explain basics to the founder.
- **Set expectations before the data arrives.** Write what you expect and what would make you change course, then compare.

## 12. Watch competitors before you plan or claim

A competitor-watch task should be standing, not occasional. We did our competitor research once, never repeated it, and a free open-source rival launched during our own launch week. We found out from the founder, not from our process.

- **Run it on a schedule** (we run it three times a week) and write the output to a folder the planners read.
- **Before any product plan, price change or comparison claim,** search for current alternatives and name them to the decision-maker.
- **Never claim "better than X"** without measuring both on the same independent test (section 7).
- **Record what you checked and when.** Competitor facts go stale quickly.

## 13. Kill or keep

At each gate, one of four outcomes, and a date:

- **Keep and ship.** The "solved when" test passed, the hands-on test passed, and the claims are backed.
- **Keep and fix.** The test failed in a specific, understood way. Write the fix and re-run.
- **Park.** The pain is real but the evidence is thin, or the cost is too high for now. Write down what evidence would reopen it.
- **Kill.** No sourced pain, the test cannot be made measurable, or the incumbent already solves it well enough. Archive the work (move it, do not delete), and note why.

Killing is cheap when the pain map is honest, because you can point at the row that says there is no evidence. Review the "weak or missing evidence" list every cycle. Some items earn their way up, and some should be dropped for good.

## 14. Worked examples

Both examples use public facts about DJ software and describe the method, not our results.

### Example A: moving a library between DJ apps

**Source.** Public forum threads and trade articles where DJs describe switching from one DJ app to another and losing cue points, colours, crates or beat grids. Each thread is logged with its link and a short quote.

**Pain-map row.**
- Who: a DJ switching apps, or playing on gear that expects a different app's format.
- Pain: cues, colours, crates and grids come across missing or shifted.
- How often: once per switch, but each switch involves a whole library of hand-placed work.
- How badly: hours to days of rework, and lost confidence before a gig.
- What they use now: partial converters, or placing cues again by hand.

**"Solved when".** On a real library (the founder's, backed up first, restored after), import into the new tool and compare against the source library field by field: every crate present, every cue at the same time position within a stated tolerance, colours and names preserved, grids equal. Any field that cannot be preserved is listed, not hidden. Nothing is claimed as lossless until a real library has passed.

**Non-goals.** Editing the source app's database in place. Touching the cloud.

**What the method changed.** Because the test had to run on a real library, the claim stayed at "tested on this library, with these known gaps" until it had. It also kept us from saying "playlists go missing" or any other symptom we had not seen sourced.

### Example B: a USB ready for CDJs without the incumbent app

**Source.** Public notices and trade coverage of USB export problems with the usual workflow, plus many forum threads from DJs whose drive failed to load tracks at the venue after checking it at home.

**Pain-map row.**
- Who: a DJ who plays club gigs from a USB drive.
- Pain: the drive misbehaves at the venue, and the DJ finds out on the night.
- How often: every gig, so even a small failure rate matters.
- How badly: very high. A failure in the booth is public.
- What they use now: re-exporting, checking tracks one by one, bringing a backup drive.

**"Solved when".** The export tool writes the format that each class of hardware reads, runs a built-in check (every track has a waveform, a grid and its cues), and is tested on named models. Models we have not tested are not in the claim.

**Non-goals.** Claiming "works on all players". Anything about a model without a physical test.

**What the method changed.** The cheap, honest first step was to measure what each hardware generation reads, then decide the output formats from that. The pain map also made clear that the product inherits the underlying problem (different players read different formats), which is a reason to test on hardware before saying "works".

## 15. Templates and starter checklist

Templates in this repo (use freely):

- `templates/pain-map.md`: the pain map table with an example row and a weak-evidence list.
- `templates/problem-brief.md`: one page per build: problem, evidence, "solved when" test, non-goals.
- `templates/claim-check.md`: a ledger that links each public claim to a test you ran.

If you only do five things:

1. Start a pain map and put a quote and link on every row. Mark thin evidence as thin.
2. Write the "solved when" test before anyone writes code.
3. Score against an independent answer key, with the incumbent as a contestant.
4. Make the founder or a real user try the installed build before you call it ready.
5. Check every sentence of public copy against the claims ledger and against the people who actually have the problem.

## Licence

CC BY 4.0. See `LICENSE`. Templates may be used freely.
