# Worksheet — Phase 4: Project anatomy

**Name:** ___________________________

Read `handouts/project-anatomy.md` first.

---

### 1. Package to path

A class declares:

```java
package edu.northeastern.shelter;
```

Its file is called `Animal.java`. **Write the full path from the project root:**

`src/____________________________________________________`

---

### 2. The deep folders

**Why is the folder chain so deep? Give the actual reason, not "it is the convention".**

<br><br><br>

---

### 3. Break it on purpose

You move `Greeting.java` up one directory, leaving the `package` line untouched.

**What happens, and at what moment — writing, compiling, or running?**

<br><br>

---

### 4. main vs test

| | `src/main/java` | `src/test/java` |
|---|---|---|
| What lives here? | | |
| Shipped to a user? | | |
| Can use JUnit? | | |

---

### 5. The same package, twice

`Greeting` is in `edu.northeastern.setup`. So is `GreetingTest`.

**Why is that deliberate? What does the test gain by sharing the package?**

<br><br><br>

---

### 6. Access modifiers

For each, say who can see it:

| Declaration | Who can see it |
|---|---|
| `public int x;` | |
| `private int x;` | |
| `int x;` *(no modifier)* | |

**Which one depends on packages existing to mean anything at all?**

<br>

---

### 7. Where does your work go?

| File | Which folder? |
|---|---|
| A new class you wrote | |
| A test you wrote | |
| `LLM-Evaluation.md` | |
| Your code-walk video | |
