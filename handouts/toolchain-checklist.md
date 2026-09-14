# Handout — The toolchain checklist

One page. Three checks. Work down it in order; each one depends on the one above.

---

## 1. Java 21

```bash
java -version
javac -version
```

**Want:** both report `21` — e.g. `openjdk version "21.0.5"`.

| You see | Do this |
|---|---|
| `21.x` | ✅ Move on. |
| `17.x`, `23.x`, `1.8` | You have a JDK, wrong version. Install 21 (Assignment 00's `installing-java.md` §1). |
| `command not found` | No JDK on your `PATH`. Install 21, then **open a new terminal**. |
| `java` works, `javac` does not | You have a *runtime*, not a *kit*. You need the **JDK**. |

**macOS — see everything you have installed:**
```bash
/usr/libexec/java_home -V
```
**Quick install (macOS):** `brew install --cask temurin@21`
**Quick install (Windows):** `winget install EclipseAdoptium.Temurin.21.JDK`

> Java 21 is not optional. Some assignments use language features that older JDKs reject outright —
> the code will not compile, and the error will not say "wrong Java version".

---

## 2. An editor with Java support

**VS Code — the supported path.**

- [ ] VS Code installed — <https://code.visualstudio.com>
- [ ] Extension: **Extension Pack for Java** (Microsoft)
- [ ] Extension: **Gradle for Java** (Microsoft)

**IntelliJ IDEA Community** — fine if you already know it. These are plain Gradle projects.

**The test that it actually works:** open a project, hover over a class name, and get a tooltip.
No tooltip means Java support is not running — the commonest cause is the wrong folder (§3 below).

---

## 3. Open the right folder

> **Open the folder that contains `build.gradle`.**

Not the parent. Not `src`. Not the folder holding several assignments.

```
Assignment00/          ← OPEN THIS ONE
├── build.gradle       ← because this is here
├── gradlew
└── src/
    ├── main/java/...
    └── test/java/...
```

**Symptoms of getting this wrong:** no syntax highlighting on Java files, no hover, no
autocomplete, "classpath is incomplete", or every import underlined in red.

**Fix:** reopen the correct folder, then in VS Code run Command Palette →
*"Java: Clean Java Language Server Workspace"* and reload the window.

---

## 4. An LLM assistant

At least one, signed in, answering. Ideally more than one — they all meter usage differently and
running out mid-assignment is an avoidable problem.

- [ ] **Claude** — Northeastern provides access
- [ ] **Cursor** — student tier
- [ ] **Kiro** — free tier
- [ ] **GitHub** — Student Developer Pack

---

## Done?

All four ticked means you are set up for the entire term. Nothing later in the course needs anything
installed beyond this — **you never install Gradle, and you never install JUnit**; the wrapper
(`./gradlew`) fetches both.
