# Handout — Anatomy of every project in this course

All ten deliverables and both team-project repos have this shape. Learn it once.

```
Assignment00/
├── README.md                  the spec — what you are building, and why
├── how-to-submit.md           deliverables, the rubric, the steps
├── code-walk.md               what your video has to explain
├── build.gradle               what the project needs; Java version pinned here
├── settings.gradle            the project's name
├── gradlew, gradlew.bat       THE WRAPPER — how you run everything
├── gradle/wrapper/            the wrapper's own files. Ignore them.
├── config/checkstyle/         the style rules your code is checked against
├── src/
│   ├── main/java/edu/northeastern/.../   your program
│   └── test/java/edu/northeastern/.../   the JUnit tests
├── submission/                your written deliverables go HERE
└── professor-feedback/        empty now; marked work comes back here
```

---

## 1. A package is a named group of classes

First line of every Java file in this course:

```java
package edu.northeastern.setup;
```

That says: this class lives in the package `edu.northeastern.setup`. Its real,
**fully-qualified name** is `edu.northeastern.setup.Greeting`.

Packages exist for three concrete reasons:

1. **No name collisions.** Java's own library has both `java.util.List` and `java.awt.List`. Both
   can exist because the packages differ.
2. **Organisation.** Related classes sit together.
3. **Access control.** A member with no `public`/`private`/`protected` is *package-private* —
   visible only inside its own package. The package is the boundary that makes that mean something.

**Naming convention: reverse domain.** Northeastern owns `northeastern.edu`, so packages start
`edu.northeastern`. Nobody else will ever own that prefix, which is the point.

## 2. Packages are folders — enforced

```
src/main/java/edu/northeastern/setup/Greeting.java
              └──────────┬──────────┘
              one folder per dot in the package name
```

The compiler checks this. Move the file up one directory and the build fails. **The deep folder
chain is not bureaucracy — it is the package name written out as directories.**

## 3. `main` and `test` are parallel trees

```
src/
├── main/java/edu/northeastern/setup/    Greeting.java, Main.java
└── test/java/edu/northeastern/setup/    GreetingTest.java
```

Gradle calls each tree a **source set**:

- **`main`** is the program. It is what ships.
- **`test`** is the JUnit tests. Compiled with extra libraries the main code never sees, and **not**
  part of the shipped program.

They deliberately use the **same package name**. Because `GreetingTest` sits in the same package as
`Greeting`, it can reach package-private members without anything being made `public` just to be
testable.

## 4. The wrapper

`gradlew` is not Gradle. It is a small script that downloads and runs **the exact Gradle version
this project expects**.

```bash
./gradlew test        # ✅ always this
gradle test           # ❌ never this
```

A Gradle you installed yourself is a different version, and the failures it produces are strange and
hard to attribute. This is why Assignment 00's `installing-java.md` says, in bold, not to install Gradle.
