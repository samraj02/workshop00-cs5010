# Workshop 01: Setup — Your Environment & the Weekly Loop

**Name:** ___________________________  **Date:** Monday, September 14, 2026

---

## Workshop Overview

Today has no design content in it. The goal is that your machine works, you have run the loop you
will run every week for the rest of the term, and you have pushed code to a repository.

**Assignment 00 is released at 5:00 PM today** and is essentially this workshop done alone. If you
finish everything here, you are most of the way through it.

Write down what breaks. Genuinely — there is a box for it in every phase. The things that break
today are the things that will break again in week 6, and a note from yourself is faster than
rediscovering the fix.

---

## Phase 1: Does your toolchain work? (25 min)

Work through `handouts/toolchain-checklist.md`. Three checks, in order. **Do not skip ahead if one
fails** — raise a hand, that is what the room is for.

**Check 1 — Java.** In a *new* terminal:

```bash
java -version
javac -version
```

- [ ] Both print **21** (e.g. `openjdk version "21.0.5"`)

> Printed 17, 23, or "command not found"? Follow `installing-java.md` §1, in your **Assignment 00** repo.
> On macOS `/usr/libexec/java_home -V` lists every JDK you have.

**Check 2 — Editor.** VS Code is what this course supports; IntelliJ is fine if you know it.

- [ ] Editor installed
- [ ] **VS Code only:** *Extension Pack for Java* and *Gradle for Java* both installed

**Check 3 — An LLM assistant.** At least one, signed in and answering. (Claude via Northeastern,
Cursor, Kiro, GitHub — see the pre-term email.)

- [ ] At least one assistant responds to "hello"

**What broke, and what fixed it:**

<br><br><br>

---

## Phase 2: Open a real Gradle project (20 min)

Your instructor will point you at a project to open. Whatever you open, the rule is the same and it
is the single most common mistake in this course:

> **Open the folder that *contains* `build.gradle`.** Not its parent. Not `src`.

- [ ] Project opened
- [ ] Java support is live — hover a class name and you get a tooltip, not silence
- [ ] Your editor is pointed at **JDK 21**
      *(VS Code: Command Palette → "Java: Configure Java Runtime")*

> **If Java features are dead** — no hover, no red squiggles, "classpath is incomplete" — you almost
> certainly opened the wrong folder. Reopen, then Command Palette → *"Java: Clean Java Language
> Server Workspace"* and reload.

**What broke, and what fixed it:**

<br><br><br>

---

## Phase 3: The weekly loop (25 min)

This is the loop. You will run it every week from now until December.

```bash
./gradlew test                          # compile + run the tests
./gradlew jacocoTestReport checkstyleMain   # coverage + style reports
```

Work through `worksheets/phase3-loop-worksheet.md`. You are asked to:

1. Run the tests and **record how many pass and how many fail**.
2. Read one failure and write down, in your own words, **what the test wanted**.
3. Make it pass.
4. Re-run and confirm.

- [ ] Tests run
- [ ] I can find the coverage report on disk
- [ ] I can find the checkstyle report on disk

**The distinction that matters all term:**

| What you see | What it means |
|---|---|
| *Tests failed* | Normal. The stubs are not written yet. **This is the correct starting state.** |
| *Build error / compile error* | Not normal. Something is wrong with the setup, not the code. Ask. |

Never install Gradle yourself. `./gradlew` is the **wrapper** — it downloads the exact Gradle version
everyone else is using. A hand-installed Gradle is a different version and will bite you.

**What broke, and what fixed it:**

<br><br><br>

---

## Phase 4: Why the project looks like this (20 min)

Read `handouts/project-anatomy.md` and complete `worksheets/phase4-anatomy-worksheet.md`.

Three ideas, and every repo this term is built on them:

**1. A package is a named group of classes**, and its name is written in the first line of the file:

```java
package edu.northeastern.setup;
```

**2. Packages are folders.** Each dot is a directory level. This is enforced by the compiler — a file
in the wrong folder does not compile:

```
src/main/java/edu/northeastern/setup/Greeting.java
              └────────┬────────┘
              one folder per package segment
```

**3. `main` and `test` are parallel trees** with the same package structure:

```
src/
├── main/java/...   ← the program
└── test/java/...   ← the JUnit tests (never shipped)
```

Answer on the worksheet:

- [ ] Why is the folder chain so deep? Give the actual reason, not "convention".
- [ ] What breaks if `Greeting.java` is moved up one folder?
- [ ] Why do the tests sit in the **same package name** as the code they test?

---

## Phase 5: Commit and push (20 min)

The submission mechanism for the entire term. There is no upload button.

```bash
git add -A
git commit -m "Workshop 01: setup"
git push
```

- [ ] `git push` succeeded
- [ ] I can see my commit on GitHub in a browser

> **Nothing is submitted until it is pushed.** A commit sitting on your laptop is not a submission,
> and "it was committed locally" is not something that can be marked.

**What broke, and what fixed it:**

<br><br><br>

---

## Phase 6: Your LLM assistant (10 min)

This course is designed to be worked through alongside an assistant, and every assignment includes a
step where one critiques your code and you respond.

Try it once, now, on something trivial:

> *"Here is a Java class. What would you criticise about it, and what would you leave alone?"*

- [ ] I got an answer
- [ ] I found **one thing in it I disagree with**

That second box is the real exercise. Disagreeing with a plausible-sounding critique, with a reason,
is a graded skill in this course — not a transgression.

---

## Wrap-Up (5 min)

**Assignment 00 releases at 5:00 PM today, due Friday Sep 18 at 5:00 PM.** It asks for:

- your name in `Greeting.STUDENT_NAME`, tests green
- `submission/Greeting.java`
- `submission/LLM-Evaluation.md`
- a push
- a ~1-minute code-walk video (due the following Tuesday) — see `code-walk.md` in the repo

If everything above is ticked, you have already done most of it.

**Before you leave, make sure these are true:**

- [ ] `java -version` says 21
- [ ] A Gradle project opens and `./gradlew test` runs
- [ ] I have pushed a commit
- [ ] An LLM assistant is signed in

**Anything still unticked is what Wednesday's recitation is for.** Bring it.

---

## Quick Reference

```bash
java -version                  # must say 21
./gradlew test                 # compile + run tests
./gradlew jacocoTestReport     # coverage  -> build/reports/jacoco/test/html/index.html
./gradlew checkstyleMain       # style     -> build/reports/checkstyle/
./gradlew build                # roughly all of the above
git add -A && git commit -m "..." && git push
```

| Symptom | First thing to check |
|---|---|
| No Java features in VS Code | Did you open the folder with `build.gradle` in it? |
| Wrong Java version | New terminal. Then `JAVA_HOME`. |
| `gradle: command not found` | You want `./gradlew`, not `gradle`. |
| Tests fail on a fresh clone | That is correct. Stubs are unwritten. |
| *Build* fails on a fresh clone | Not correct. Ask. |
