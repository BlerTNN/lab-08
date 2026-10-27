# CMPUT 301: Lab 8 Participation Exercise

## Student Details
- **Full Name:** `Yuduo Tian`
- **CCID:** `yuduo1`

## References and Resources
- [Lab 8 instructions and starter code](lab-08-description.md).
- CMPUT 301, *2026-Lab 8 Slides.pdf*, Michelle Deng, University of Alberta.
- OpenAI Codex assisted with implementation, tests, build verification, and documentation.

## Verbal Collaboration
N/A

## Implementation
- `restoreMana(amount)` adds mana and caps the result at 100.
- `train()` increases spell power by 1 and spends 5 mana when mana is at least 5;
  otherwise, both values remain unchanged.
- Tests cover restoration below and above the cap, training with 30 mana,
  exactly 5 mana, and insufficient mana (4).
- CI uses Java 21 to match the project's Gradle daemon configuration.

## Local Validation and TDD History
From the repository root, with the Android SDK configured:

```bash
cd lab8
./gradlew build --configuration-cache
```

The following stages were executed locally, in order, on October 27, 2026.
The failing tests were run and committed before their implementations.

| Commit | Stage | Local result |
| --- | --- | --- |
| `f1b1b1b` | Baseline; align CI JDK and wrapper permissions | Build passes; 3 tests pass |
| `376eadc` | Empty `restoreMana()` and restoration tests | Build fails; 2 of 5 tests fail |
| `3e082ca` | Implement `restoreMana()` | Build passes; 5 tests pass |
| `d8fa747` | Empty `train()` and training tests | Build fails; 2 of 8 tests fail |
| `06c4cf8` | Implement `train()` | Build passes; 8 tests pass |

The final build also assembles debug/release APKs and passes Android lint.
Device instrumentation tests were not run; the lab's CI command runs local unit tests.
Local phase-specific JUnit XML reports and red/green build logs are saved under
`.git/lab08-validation/` (local only, not part of the submission).

## Pending GitHub Actions and Submission
No commits have been pushed, and no new GitHub Actions runs have been triggered.
Local results do not replace the lab's required failing and passing Actions runs.

When ready to publish, enable workflows in the repository's
[Actions tab](https://github.com/BlerTNN/lab-08/actions) if prompted.
Push the following commits **one at a time**, waiting for each Actions run to
finish and checking its expected result in the table above before continuing:

```bash
git push origin f1b1b1b:refs/heads/main
git push origin 376eadc:refs/heads/main
git push origin 3e082ca:refs/heads/main
git push origin d8fa747:refs/heads/main
git push origin 06c4cf8:refs/heads/main
git push origin main
```

Do not push only the final commit first: that would skip the Actions runs for
the intentionally failing stages. No force push is needed.

After verifying the required Actions results and public repository access,
submit `https://github.com/BlerTNN/lab-08` on Canvas. This submission has not been made.
