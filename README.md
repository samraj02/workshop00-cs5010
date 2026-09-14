# Workshop 01: Setup — Your Environment & the Weekly Loop

**Course**: CS 5004/5010 — Object-Oriented Design
**Date**: Monday, September 14, 2026 (Week 1)
**Duration**: 2 hours
**Format**: Laptops required — this is a working session, not a lecture

---

## Overview

The first workshop of the term, and the only one whose subject is the machinery rather than the
material. Every student leaves with a working Java toolchain, a Gradle project that builds, a repo
they have pushed to, and one run of the weekly loop behind them.

This is deliberately the least intellectually demanding session of the term. It is also the one with
the highest cost of failure: a student whose environment is broken in week 1 loses week 2 as well,
and week 2 is when the graded work starts.

**It pairs with Assignment 00**, which releases at **5:00 PM the same day** and is due Fri Sep 18.
The workshop is the rehearsal; the assignment is the same loop run alone.

> **Module 0** — *Course Setup & Java Environment*. Quiz 00 is due the day before (Sun Sep 13),
> so students arrive having at least watched the material.

---

## Learning Objectives (Module 00)

By the end of this workshop, students should be able to:

- [ ] Verify their JDK is **21** and fix it if it is not
- [ ] Open a Gradle project in their editor with Java support working
- [ ] Run `./gradlew test`, read the result, and distinguish a **failing test** from a **build error**
- [ ] Explain what the Gradle wrapper is and why they must never install Gradle themselves
- [ ] Navigate `src/main/java` vs `src/test/java` and explain why the folders are nested so deeply
- [ ] Commit and push to their assignment repository
- [ ] Have at least one LLM assistant signed in and answering

---

## Why setup gets a whole workshop

Three reasons, worth stating to the students:

1. **Every repo this term is identical in shape.** Learn the layout once, on something with nothing
   at stake, and the remaining nine deliverables are navigation rather than discovery.
2. **The failure modes are boring and specific.** Wrong JDK, wrong folder opened, Gradle installed
   by hand. Each costs an evening alone and two minutes with an instructor in the room.
3. **Assignment 00 releases at 5 PM today.** Anyone who finishes here has already done most of it.

---

## Materials Needed

### Students bring
- A laptop, charged.
- Ideally: JDK 21 and an editor already installed, per the pre-term email. **Assume perhaps half the
  room has not.** Phase 1 exists for them.

### Provided
- `Student-Workbook.md` — the phases, with space to record what broke and how it was fixed.
- `handouts/toolchain-checklist.md` — the one-page "am I set up?" test.
- `handouts/project-anatomy.md` — the annotated folder tree.
- `worksheets/phase3-loop-worksheet.md`, `worksheets/phase4-anatomy-worksheet.md`
- `solutions/` — expected answers for the two worksheets.
- `Instructor-Guide.md` — triage order, the common breakages, and timing.

### Instructor materials
- A machine on the projector to demonstrate the loop.
- **Reference:** `installing-java.md` in the **Assignment 00** repo is the authoritative install
  guide, and the only copy. Do not restate it here, point at it.

---

## Workshop Structure

| Phase | Duration | Type | Activity |
|-------|----------|------|----------|
| 1 | 25 min | Triage | JDK 21 verified; editor + Java extensions installed |
| 2 | 20 min | Guided | Open a Gradle project; confirm Java support is live |
| 3 | 25 min | Independent | Run the weekly loop — test, read the failure, fix, re-run |
| 4 | 20 min | Read | Project anatomy: packages are folders, `main` vs `test` |
| 5 | 20 min | Independent | Commit and push; the submission workflow |
| 6 | 10 min | Independent | Sign in to an LLM assistant and run one prompt |
| — | 5 min | Wrap-up | What Assignment 00 asks, released at 5 PM today |

**Phase 1 is the only one with a hard dependency.** Nobody proceeds past it broken — pair anyone
still stuck with someone who is working, and keep circulating. Everything after Phase 1 can be
attempted out of order by students who arrive already set up.

---

## Connection to Course

- **Assignment 00** (released 5:00 PM today, due Fri Sep 18) is this workshop run solo, plus a name
  in `Greeting.java` and an LLM self-evaluation.
- **Workshop 02** (Sep 21) is the first session that assumes a working toolchain and spends none of
  its time on one.
- **The layout learned in Phase 4** is the layout of all ten deliverables and the team project.

---

## Notes

- **This workshop replaced an earlier one** titled *Introduction to Object-Oriented Thinking*, which
  taught Module 1 material on Module 0's date. That content moved into Workshops 02 and 03, where it
  matches the module being taught. See `PlanningDocuments/125-timeline-analysis.md` §F2.
- **Do not let this run long.** If a student's machine is genuinely broken after 45 minutes, that is
  an office-hours problem, not a workshop problem — get them working on a classmate's machine and
  keep the room moving.
