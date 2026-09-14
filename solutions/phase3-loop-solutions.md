# Solutions — Phase 3: The weekly loop

**Instructor notes.** The point of this phase is not the fix; it is that students can *read* a test
failure and tell it apart from a build error. Push for phrasing in their own words.

---

**1.** Numbers vary. **Yes**, failures are correct on a fresh assignment: every stub throws
`UnsupportedOperationException` and every stub is covered by at least one provided test. A fresh
clone with everything green would mean the work was already done.

**2.** Looking for a plain-English statement of the contract — "it wanted `of(-7)` to throw rather
than build an object" — not a paraphrase of the assertion. The file/method should be identifiable
from the test name and the stack trace; if a student cannot find it, walk them through reading the
top frame that names a course class.

**3.** Passed goes up by one.

**4.**
- **Test failure** — the code compiled and ran, and behaved differently from what was asked. Normal
  and expected; it is the to-do list.
- **Build error** — it did not compile. Nothing ran at all. On a fresh clone this means the
  environment is wrong, not the code.
- **The build error.** A student sitting on a build error is blocked and cannot start.

**5.** Paths look like
`<project>/build/reports/jacoco/test/html/index.html` and `<project>/build/reports/checkstyle/main.html`.
Coverage is a poor target because the **provided** suite already pushes it high — a student can add
nothing and still see a good number. It is a diagnostic for finding untested code, not a score.

**6.** `./gradlew` is the **wrapper**: it downloads and runs the exact Gradle version the project
pins. `gradle` is whatever happens to be on the machine. A version mismatch produces failures that
look like code problems and are not — which is why the install docs say not to install Gradle.
