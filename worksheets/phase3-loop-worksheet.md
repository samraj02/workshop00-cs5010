# Worksheet — Phase 3: The weekly loop

**Name:** ___________________________

---

### 1. Run the tests

```bash
./gradlew test
```

Tests passed: ________   Tests failed: ________

Is that the correct starting state for a fresh assignment? **Yes / No** — why?

<br><br>

---

### 2. Read one failure

Pick one failing test. Copy its name:

`________________________________________`

**In your own words — not copied from the output — what did that test want the code to do?**

<br><br><br>

**Which file and method would you have to change to satisfy it?**

<br><br>

---

### 3. Make it pass, then re-run

Tests passed now: ________   Tests failed now: ________

---

### 4. Failing vs broken

Write the difference in one sentence each.

**A test failure means:**

<br><br>

**A build error means:**

<br><br>

**Which of the two should make you ask for help immediately?**

<br>

---

### 5. Find the reports

```bash
./gradlew jacocoTestReport checkstyleMain
```

Full path to the coverage report on your machine:

`________________________________________________________`

Full path to the checkstyle report:

`________________________________________________________`

**Coverage says a number. Why is that number a poor target to aim at in this course?**
*(The provided tests already cover almost every line.)*

<br><br>

---

### 6. The wrapper

**Why must you run `./gradlew test` rather than `gradle test`?**

<br><br>

**What would go wrong if you installed Gradle yourself and used that?**

<br><br>
