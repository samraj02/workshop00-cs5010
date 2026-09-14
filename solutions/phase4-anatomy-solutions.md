# Solutions — Phase 4: Project anatomy

**1.** `src/main/java/edu/northeastern/shelter/Animal.java`

**2.** Because **the compiler enforces that the package name matches the directory path.** The
folders are not decoration — they *are* the package name written out. Accept any answer that gets to
enforcement; reject "that is just how Java does it".

**3.** It fails **at compile time**, and the message is about the package declaration not matching
the location. Worth stressing: this is caught early and loudly, which is the good case.

**4.**

| | `src/main/java` | `src/test/java` |
|---|---|---|
| What lives here? | The program itself | JUnit tests |
| Shipped to a user? | Yes | No |
| Can use JUnit? | No | Yes — it is on the test classpath only |

**5.** Because a test in the **same package** can reach **package-private** members. Without that,
things would have to be made `public` purely to be testable — which weakens encapsulation for a
reason that has nothing to do with the design.

**6.**

| Declaration | Who can see it |
|---|---|
| `public int x;` | Everyone, any package |
| `private int x;` | Only this class |
| `int x;` | Any class **in the same package** |

**Package-private** is the one that needs packages to mean anything.

**7.**

| File | Folder |
|---|---|
| A new class | `src/main/java/<package path>/` |
| A test | `src/test/java/<package path>/` |
| `LLM-Evaluation.md` | `submission/` |
| Code-walk video | **Not in the repo at all** — uploaded to Canvas |

That last row catches people out every term.
