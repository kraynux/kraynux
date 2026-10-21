# Development procedure — [PROJECT_NAME]

| Field | Value |
|---|---|
| Project | [PROJECT_NAME] |
| Target version | [TARGET_VERSION] |
| Owner | [NAME] |
| Creation date | [YYYY-MM-DD] |
| Last update | [YYYY-MM-DD] |
| Overall status | Draft / In progress / Validated / In production |
| Target environment | [Linux / Debian / Server / Workstation] |
| Main language | [Python / Bash / Lua / Other] |
| Repository | [URL_OR_PATH] |

## Cross-cutting rules

- [ ] No code is written before the final plan is validated.
- [ ] Every important decision is documented.
- [ ] Every anomaly is recorded.
- [ ] Every fix is tested.
- [ ] Every behavior change is documented.
- [ ] Backups are made before any production intervention.
- [ ] The AI analyzes and proposes; the human decides, validates, and deploys.
- [ ] The code remains aligned with the final documentation.

## Global phase tracking

| Phase | Actor | Main deliverable | Status | Validation date |
|---:|---|---|---|---|
| 1 | Human | Needs and design | [ ] | [YYYY-MM-DD] |
| 2 | Human | Architecture draft and preliminary plan | [ ] | [YYYY-MM-DD] |
| 3 | AI | Analysis, side effects, final plan | [ ] | [YYYY-MM-DD] |
| 4 | Human | Project core coded | [ ] | [YYYY-MM-DD] |
| 5 | AI | Code audit, fixes, and tests | [ ] | [YYYY-MM-DD] |
| 6 | Human | Real production tests | [ ] | [YYYY-MM-DD] |
| 7 | AI | Fix plan and final coding | [ ] | [YYYY-MM-DD] |
| 8 | Human | Final testing | [ ] | [YYYY-MM-DD] |
| 9 | Human | Documentation draft | [ ] | [YYYY-MM-DD] |
| 10 | AI | Final documentation | [ ] | [YYYY-MM-DD] |
| 11 | Human | Production deployment | [ ] | [YYYY-MM-DD] |

---

# Phase 1 — Reflection, needs, usage, and design

**Actor: Human**  
**Goal:** define the problem, users, real usage, constraints, and project boundaries.

## 1. Initial problem

- Identified problem: [TO BE COMPLETED]
- Current situation: [TO BE COMPLETED]
- Consequence of the problem: [TO BE COMPLETED]
- Project objective: [TO BE COMPLETED]

## 2. Target users

| User | Main need | Technical level | Intended usage |
|---|---|---|---|
| [User 1] | [TO BE COMPLETED] | [Beginner / Technical / Expert] | [TO BE COMPLETED] |
| [User 2] | [TO BE COMPLETED] | [Beginner / Technical / Expert] | [TO BE COMPLETED] |

## 3. Usage scenarios

### Nominal scenario

- Context: [TO BE COMPLETED]
- User action: [TO BE COMPLETED]
- Expected result: [TO BE COMPLETED]

### Edge-case scenario

- Context: [TO BE COMPLETED]
- User action: [TO BE COMPLETED]
- Expected result: [TO BE COMPLETED]

### Error scenario

- Context: [TO BE COMPLETED]
- User action: [TO BE COMPLETED]
- Expected result: [TO BE COMPLETED]

### Forbidden or dangerous scenario

- Context: [TO BE COMPLETED]
- Expected behavior: [Refusal / Warning / Blocking / Logging]
- Justification: [TO BE COMPLETED]

## 4. Features

### Mandatory

- [ ] [Feature 1]
- [ ] [Feature 2]
- [ ] [Feature 3]

### Useful but deferrable

- [ ] [Feature 1]
- [ ] [Feature 2]

### Optional

- [ ] [Feature 1]

### Excluded

- [ ] [Excluded feature]
- Justification: [TO BE COMPLETED]

## 5. Constraints

| Area | Constraint | Priority |
|---|---|---|
| System | [Linux / Debian / Version] | [High / Medium / Low] |
| Language | [Python / Bash / Lua] | [High / Medium / Low] |
| Dependencies | [TO BE COMPLETED] | [High / Medium / Low] |
| Performance | [TO BE COMPLETED] | [High / Medium / Low] |
| Security | [TO BE COMPLETED] | [High / Medium / Low] |
| Compatibility | [TO BE COMPLETED] | [High / Medium / Low] |
| Maintenance | [TO BE COMPLETED] | [High / Medium / Low] |
| Deployment | [TO BE COMPLETED] | [High / Medium / Low] |

## 6. Identified risks

| Risk | Impact | Probability | Prevention measure |
|---|---|---|---|
| [Risk 1] | [Low / Medium / High] | [Low / Medium / High] | [TO BE COMPLETED] |
| [Risk 2] | [Low / Medium / High] | [Low / Medium / High] | [TO BE COMPLETED] |

## 7. Decisions made

| ID | Decision | Justification | Date |
|---:|---|---|---|
| D-001 | [TO BE COMPLETED] | [TO BE COMPLETED] | [YYYY-MM-DD] |
| D-002 | [TO BE COMPLETED] | [TO BE COMPLETED] | [YYYY-MM-DD] |

## 8. Open questions

- [ ] [Question 1]
- [ ] [Question 2]

## Phase 1 validation

- [ ] The problem is clearly formulated.
- [ ] Users are identified.
- [ ] Main usage scenarios are described.
- [ ] Mandatory features are listed.
- [ ] Project boundaries are explicit.
- [ ] Technical constraints are known.
- [ ] Main risks are identified.

**Status:** [ ] Draft / [ ] Validated  
**Validated by:** [NAME]  
**Date:** [YYYY-MM-DD]

---

# Phase 2 — Draft, main components, and development plan

**Actor: Human**  
**Goal:** turn the needs into a logical architecture and an actionable development plan.

## 1. Main components

| Component | Responsibility | Must not do | Priority |
|---|---|---|---|
| Interface / CLI | [TO BE COMPLETED] | [TO BE COMPLETED] | [High / Medium / Low] |
| Business core | [TO BE COMPLETED] | [TO BE COMPLETED] | [High / Medium / Low] |
| Configuration | [TO BE COMPLETED] | [TO BE COMPLETED] | [High / Medium / Low] |
| Data models | [TO BE COMPLETED] | [TO BE COMPLETED] | [High / Medium / Low] |
| Services | [TO BE COMPLETED] | [TO BE COMPLETED] | [High / Medium / Low] |
| Storage | [TO BE COMPLETED] | [TO BE COMPLETED] | [High / Medium / Low] |
| Export | [TO BE COMPLETED] | [TO BE COMPLETED] | [High / Medium / Low] |
| Logging | [TO BE COMPLETED] | [TO BE COMPLETED] | [High / Medium / Low] |
| Security | [TO BE COMPLETED] | [TO BE COMPLETED] | [High / Medium / Low] |
| Tests | [TO BE COMPLETED] | [TO BE COMPLETED] | [High / Medium / Low] |

## 2. Main flow

```text
[User input]
    → [Interface]
    → [Validation]
    → [Business core]
    → [Services / Modules]
    → [Result]
    → [Output / Storage / Logs]
```

## 3. Planned modules

| Module | Role | Dependencies | Priority |
|---|---|---|---|
| [module_1] | [TO BE COMPLETED] | [TO BE COMPLETED] | [High / Medium / Low] |
| [module_2] | [TO BE COMPLETED] | [TO BE COMPLETED] | [High / Medium / Low] |
| [module_3] | [TO BE COMPLETED] | [TO BE COMPLETED] | [High / Medium / Low] |

## 4. Preliminary tree structure

```text
[PROJECT_NAME]/
├── src/
│   └── [project_name]/
│       ├── __init__.py
│       ├── config.py
│       ├── exceptions.py
│       ├── logging.py
│       ├── models/
│       ├── core/
│       ├── services/
│       └── cli/
├── tests/
│   ├── unit/
│   └── integration/
├── docs/
├── scripts/
└── CHANGELOG.md
```

## 5. Planned dependencies

| Dependency | Usage | Minimum version | Justification |
|---|---|---|---|
| [Dependency 1] | [TO BE COMPLETED] | [TO BE COMPLETED] | [TO BE COMPLETED] |
| [Dependency 2] | [TO BE COMPLETED] | [TO BE COMPLETED] | [TO BE COMPLETED] |

## 6. Development breakdown

| Phase | Content | Priority | Estimate |
|---:|---|---|---|
| 1 | Foundations: structure, configuration, errors, logs | [High / Medium] | [Duration] |
| 2 | Models and contracts | [High / Medium] | [Duration] |
| 3 | Business core | [High / Medium] | [Duration] |
| 4 | Interface / CLI | [High / Medium] | [Duration] |
| 5 | Storage / export | [High / Medium] | [Duration] |
| 6 | Tests | [High / Medium] | [Duration] |
| 7 | Documentation and packaging | [High / Medium] | [Duration] |

## Phase 2 validation

- [ ] Main components are identified.
- [ ] Each module has a clear responsibility.
- [ ] Main flows are described.
- [ ] The preliminary tree structure is defined.
- [ ] Main dependencies are identified.
- [ ] The development order is defined.
- [ ] No development has started.

**Status:** [ ] Draft / [ ] Validated  
**Validated by:** [NAME]  
**Date:** [YYYY-MM-DD]

---

# Phase 3 — AI analysis, side effects, and final plan

**Actor: AI**  
**Goal:** analyze the human-produced documents, identify risks, and produce an actionable final plan.

## 1. Documents analyzed

- [ ] `PROJECT_00_NEEDS_AND_DESIGN.md`
- [ ] `PROJECT_01_ARCHITECTURE_DRAFT.md`
- [ ] `PROJECT_02_DEVELOPMENT_PLAN_DRAFT.md`
- [ ] [Other document]

## 2. AI analysis prompt

```text
Analyze this project without writing code.

1. Detect inconsistencies.
2. Detect missing functions.
3. Detect misplaced responsibilities.
4. Identify possible side effects.
5. Identify failure cases.
6. Identify security risks.
7. Identify compatibility issues.
8. Propose a more robust project structure.
9. Propose a final development plan.
10. Indicate the points that must remain under human decision.
```

## 3. Detected inconsistencies

| ID | Description | Impact | Proposal | Human decision |
|---:|---|---|---|---|
| A-001 | [TO BE COMPLETED] | [Low / Medium / High] | [TO BE COMPLETED] | [Accepted / Rejected / Deferred] |
| A-002 | [TO BE COMPLETED] | [Low / Medium / High] | [TO BE COMPLETED] | [Accepted / Rejected / Deferred] |

## 4. Identified side effects

| ID | Side effect | Trigger | Impact | Prevention | Status |
|---:|---|---|---|---|---|
| SE-001 | [TO BE COMPLETED] | [TO BE COMPLETED] | [Low / Medium / High] | [TO BE COMPLETED] | [Open / Handled / Accepted] |
| SE-002 | [TO BE COMPLETED] | [TO BE COMPLETED] | [Low / Medium / High] | [TO BE COMPLETED] | [Open / Handled / Accepted] |

## 5. Failure cases to anticipate

| Case | Expected behavior | Expected message / log | Associated test |
|---|---|---|---|
| Missing file | [TO BE COMPLETED] | [TO BE COMPLETED] | [TO BE COMPLETED] |
| Permission denied | [TO BE COMPLETED] | [TO BE COMPLETED] | [TO BE COMPLETED] |
| Network unavailable | [TO BE COMPLETED] | [TO BE COMPLETED] | [TO BE COMPLETED] |
| Invalid input | [TO BE COMPLETED] | [TO BE COMPLETED] | [TO BE COMPLETED] |
| User interruption | [TO BE COMPLETED] | [TO BE COMPLETED] | [TO BE COMPLETED] |
| Corrupted data | [TO BE COMPLETED] | [TO BE COMPLETED] | [TO BE COMPLETED] |

## 6. Security risks

| Risk | Scenario | Measure | Priority |
|---|---|---|---|
| [Risk 1] | [TO BE COMPLETED] | [TO BE COMPLETED] | [P0 / P1 / P2] |
| [Risk 2] | [TO BE COMPLETED] | [TO BE COMPLETED] | [P0 / P1 / P2] |

## 7. Final development plan

| Phase | Objective | Deliverables | Completion criteria | Dependencies |
|---:|---|---|---|---|
| 1 | [TO BE COMPLETED] | [TO BE COMPLETED] | [TO BE COMPLETED] | [None] |
| 2 | [TO BE COMPLETED] | [TO BE COMPLETED] | [TO BE COMPLETED] | [Phase 1] |
| 3 | [TO BE COMPLETED] | [TO BE COMPLETED] | [TO BE COMPLETED] | [Phase 2] |

## Phase 3 validation

- [ ] Inconsistencies are handled or documented.
- [ ] Side effects are identified.
- [ ] Failure cases are anticipated.
- [ ] Security risks are addressed.
- [ ] The final plan is validated by the human.
- [ ] Final decisions are recorded.

**Status:** [ ] Draft / [ ] Validated  
**Validated by:** [NAME]  
**Date:** [YYYY-MM-DD]

---

# Phase 4 — Coding the project core

**Actor: Human**  
**Goal:** develop the functional core without adding out-of-scope features.

## 1. Coding scope

- [ ] Project structure
- [ ] Virtual environment
- [ ] Dependencies
- [ ] Configuration
- [ ] Data models
- [ ] Exceptions
- [ ] Logging
- [ ] Business services
- [ ] Business core
- [ ] Unit tests
- [ ] CLI / interface
- [ ] Integration

## 2. Implementation order

| Order | Element | File / module | Status | Commit |
|---:|---|---|---|---|
| 1 | [Element] | [path] | [ ] | [hash] |
| 2 | [Element] | [path] | [ ] | [hash] |
| 3 | [Element] | [path] | [ ] | [hash] |

## 3. Commit rules

- One commit = one single intention.
- Do not mix feature, fix, and refactoring.
- Recommended message:

```text
[type]: [short description]

[type] = feat, fix, refactor, test, docs, chore
```

Example:

```text
feat: add configuration loading and validation
```

## 4. Initial tests

| Test | Objective | Command | Expected result | Status |
|---|---|---|---|---|
| [Test 1] | [TO BE COMPLETED] | [command] | [TO BE COMPLETED] | [ ] |
| [Test 2] | [TO BE COMPLETED] | [command] | [TO BE COMPLETED] | [ ] |

## Phase 4 validation

- [ ] The business core works.
- [ ] Main inputs are validated.
- [ ] Main errors are handled.
- [ ] Unit tests pass.
- [ ] The project starts in basic mode.
- [ ] No out-of-scope feature has been added.

**Status:** [ ] In progress / [ ] Validated  
**Validated by:** [NAME]  
**Date:** [YYYY-MM-DD]

---

# Phase 5 — Code analysis, correction, and AI testing

**Actor: AI**  
**Goal:** detect defects, side effects, and risks before real-world testing.

## 1. AI audit prompt

```text
Analyze the code without rewriting it entirely.

1. Check compliance with the development plan.
2. Detect probable bugs.
3. Detect side effects.
4. Detect resource leaks.
5. Detect unhandled errors.
6. Detect unvalidated inputs.
7. Detect security issues.
8. Detect performance issues.
9. Detect dead code.
10. Detect misplaced responsibilities.
11. Propose targeted fixes.
12. Propose missing tests.
```

## 2. Audit findings

| ID | File / function | Finding | Severity | Proposed fix | Status |
|---:|---|---|---|---|---|
| C-001 | [path] | [TO BE COMPLETED] | [Critical / Major / Minor] | [TO BE COMPLETED] | [Open / Fixed / Validated] |
| C-002 | [path] | [TO BE COMPLETED] | [Critical / Major / Minor] | [TO BE COMPLETED] | [Open / Fixed / Validated] |

## 3. Tests added

| Test | Objective | Test file | Status |
|---|---|---|---|
| [Test 1] | [TO BE COMPLETED] | [path] | [ ] |
| [Test 2] | [TO BE COMPLETED] | [path] | [ ] |

## Phase 5 validation

- [ ] Critical bugs are fixed.
- [ ] Side effects are handled or documented.
- [ ] Unit tests pass.
- [ ] Integration tests pass.
- [ ] The code complies with the final plan.
- [ ] Fixes have been applied progressively.

**Status:** [ ] In progress / [ ] Validated  
**Validated by:** [NAME]  
**Date:** [YYYY-MM-DD]

---

# Phase 6 — Real-world study and production testing

**Actor: Human**  
**Goal:** validate the software under real conditions and record all anomalies.

## 1. Test environment

| Item | Value |
|---|---|
| Machine | [TO BE COMPLETED] |
| System | [TO BE COMPLETED] |
| Software version | [TO BE COMPLETED] |
| Environment | [Controlled production / Staging / Real server] |
| Backup performed | [Yes / No] |
| Backup date | [YYYY-MM-DD] |
| Rollback method | [TO BE COMPLETED] |

## 2. Tested scenarios

| ID | Scenario | Command | Expected result | Actual result | Status |
|---:|---|---|---|---|---|
| T-001 | [TO BE COMPLETED] | [command] | [TO BE COMPLETED] | [TO BE COMPLETED] | [OK / KO / Partial] |
| T-002 | [TO BE COMPLETED] | [command] | [TO BE COMPLETED] | [TO BE COMPLETED] | [OK / KO / Partial] |

## 3. Observation grid

| Area | Observed item | Result | Comment |
|---|---|---|---|
| Functional | Expected function | [OK / KO] | [TO BE COMPLETED] |
| Interface | Clarity of commands | [OK / KO] | [TO BE COMPLETED] |
| Performance | Execution time | [OK / KO] | [TO BE COMPLETED] |
| Stability | No unexpected crash | [OK / KO] | [TO BE COMPLETED] |
| Errors | Understandability of messages | [OK / KO] | [TO BE COMPLETED] |
| Logs | Quality and usefulness | [OK / KO] | [TO BE COMPLETED] |
| Security | Safe behavior | [OK / KO] | [TO BE COMPLETED] |
| Compatibility | Operation on the real target | [OK / KO] | [TO BE COMPLETED] |
| Aesthetics | Readability of output | [OK / KO] | [TO BE COMPLETED] |
| Real usage | Smoothness of the workflow | [OK / KO] | [TO BE COMPLETED] |

## 4. Anomaly log

| ID | Date | Severity | Description | Logs | Hypothesis | Proposed fix | Status |
|---:|---|---|---|---|---|---|---|
| BUG-001 | [YYYY-MM-DD] | [Critical / Major / Minor / Aesthetic] | [TO BE COMPLETED] | [TO BE COMPLETED] | [TO BE COMPLETED] | [TO BE COMPLETED] | [Open / Fixed / Validated] |
| BUG-002 | [YYYY-MM-DD] | [Critical / Major / Minor / Aesthetic] | [TO BE COMPLETED] | [TO BE COMPLETED] | [TO BE COMPLETED] | [TO BE COMPLETED] | [Open / Fixed / Validated] |

## Phase 6 validation

- [ ] All critical scenarios have been tested.
- [ ] Bugs are recorded.
- [ ] Usability issues are recorded.
- [ ] Aesthetic issues are recorded.
- [ ] No critical blocking bug is ignored.

**Status:** [ ] In progress / [ ] Validated  
**Validated by:** [NAME]  
**Date:** [YYYY-MM-DD]

---

# Phase 7 — Improvement plan, fixes, and final coding

**Actor: AI**  
**Goal:** turn anomalies into prioritized fixes, then apply the required code changes.

## 1. Anomaly analysis prompt

```text
Here is the production testing log.

1. Rank anomalies by severity.
2. Group related anomalies.
3. Identify probable causes.
4. Propose a minimal fix for each anomaly.
5. Indicate regression risks.
6. Propose tests to add.
7. Propose usability improvements.
8. Propose aesthetic improvements.
9. Change only what is necessary.
10. Preserve validated behavior.
```

## 2. Anomaly prioritization

| Priority | Type | Affected anomalies | Treatment |
|---|---|---|---|
| P0 | Crash, data loss, vulnerability | [BUG-XXX] | Immediate fix |
| P1 | Incorrect feature | [BUG-XXX] | Fix before final validation |
| P2 | Poor user experience | [BUG-XXX] | Fix if reasonable |
| P3 | Aesthetics, message, format | [BUG-XXX] | Fix or defer |
| P4 | Future improvement | [BUG-XXX] | Backlog |

## 3. Applied fixes

| ID | Anomaly | Fix | Modified files | Tests added | Regression risk | Status |
|---:|---|---|---|---|---|---|
| FIX-001 | [BUG-XXX] | [TO BE COMPLETED] | [path] | [path] | [Low / Medium / High] | [Applied / Validated] |
| FIX-002 | [BUG-XXX] | [TO BE COMPLETED] | [path] | [path] | [Low / Medium / High] | [Applied / Validated] |

## Phase 7 validation

- [ ] Every anomaly has a clear status.
- [ ] Fixes are applied by priority.
- [ ] Non-regression tests pass.
- [ ] Validated behavior is preserved.
- [ ] Every fix is documented.

**Status:** [ ] In progress / [ ] Validated  
**Validated by:** [NAME]  
**Date:** [YYYY-MM-DD]

---

# Phase 8 — Final testing

**Actor: Human**  
**Goal:** validate the release candidate before final documentation and stable production deployment.

## 1. Validation tests

| Test | Objective | Command | Expected result | Actual result | Status |
|---|---|---|---|---|---|
| Nominal scenario | [TO BE COMPLETED] | [command] | [TO BE COMPLETED] | [TO BE COMPLETED] | [ ] |
| Error scenario | [TO BE COMPLETED] | [command] | [TO BE COMPLETED] | [TO BE COMPLETED] | [ ] |
| CLI options | [TO BE COMPLETED] | [command] | [TO BE COMPLETED] | [TO BE COMPLETED] | [ ] |
| Configuration | [TO BE COMPLETED] | [command] | [TO BE COMPLETED] | [TO BE COMPLETED] | [ ] |
| Permissions | [TO BE COMPLETED] | [command] | [TO BE COMPLETED] | [TO BE COMPLETED] | [ ] |
| Interruption | [TO BE COMPLETED] | [command] | [TO BE COMPLETED] | [TO BE COMPLETED] | [ ] |
| Non-regression | [TO BE COMPLETED] | [command] | [TO BE COMPLETED] | [TO BE COMPLETED] | [ ] |

## 2. Final checklist

- [ ] The project starts correctly.
- [ ] Main commands work.
- [ ] Errors are understandable.
- [ ] Logs are usable.
- [ ] No critical bug is present.
- [ ] No regression is detected.
- [ ] Performance is acceptable.
- [ ] Security meets requirements.
- [ ] The version is identifiable.
- [ ] Rollback is possible.

## Phase 8 validation

**Decision:** [ ] Release candidate / [ ] Return to correction  
**Validated by:** [NAME]  
**Date:** [YYYY-MM-DD]

---

# Phase 9 — Documentation draft

**Actor: Human**  
**Goal:** document the software as it actually works.

## 1. Documents to produce

| Document | Purpose | Status |
|---|---|---|
| `README.md` | Presentation and quick start | [ ] |
| `USER_GUIDE.md` | Detailed, accessible usage guide | [ ] |
| `TECHNICAL_GUIDE.md` | Architecture and internal operation | [ ] |
| `DEVELOPER_GUIDE.md` | Environment, tests, conventions | [ ] |
| `INSTALLATION.md` | Prerequisites and installation | [ ] |
| `SECURITY.md` | Risks, permissions, best practices | [ ] |
| `TROUBLESHOOTING.md` | Common errors and solutions | [ ] |
| `CHANGELOG.md` | Version history | [ ] |

## 2. Content to check

- [ ] Every command is documented.
- [ ] Every option is documented.
- [ ] Every configuration file is documented.
- [ ] Every dependency is documented.
- [ ] Every common error is explained.
- [ ] Limitations are explicit.
- [ ] Examples are testable.

## Phase 9 validation

**Status:** [ ] Draft / [ ] Validated  
**Validated by:** [NAME]  
**Date:** [YYYY-MM-DD]

---

# Phase 10 — Formatting and final documentation

**Actor: AI**  
**Goal:** complete, structure, and harmonize the documentation without inventing behavior not present in the code.

## 1. Documentation completion prompt

```text
Here are the documentation drafts.

1. Check consistency with the actual code.
2. Detect undocumented functions.
3. Detect undocumented CLI options.
4. Detect unexplained error messages.
5. Detect missing dependencies.
6. Detect missing installation steps.
7. Detect inconsistencies between documents.
8. Improve structure and readability.
9. Complete missing sections.
10. Do not change described behavior without evidence in the code.
```

## 2. Documentation checks

| Check | Status | Comment |
|---|---|---|
| Consistency with code | [ ] | [TO BE COMPLETED] |
| Commands documented | [ ] | [TO BE COMPLETED] |
| Options documented | [ ] | [TO BE COMPLETED] |
| Exit codes documented | [ ] | [TO BE COMPLETED] |
| Configuration documented | [ ] | [TO BE COMPLETED] |
| Dependencies documented | [ ] | [TO BE COMPLETED] |
| Common errors documented | [ ] | [TO BE COMPLETED] |
| Testable examples | [ ] | [TO BE COMPLETED] |
| Harmonized structure | [ ] | [TO BE COMPLETED] |

## Phase 10 validation

**Status:** [ ] Draft / [ ] Validated  
**Validated by:** [NAME]  
**Date:** [YYYY-MM-DD]

---

# Phase 11 — Final production deployment

**Actor: Human**  
**Goal:** deploy the validated, documented, and tested version.

## 1. Preparation

- [ ] Version validated in phase 8.
- [ ] Final documentation validated in phase 10.
- [ ] Backup of the existing environment performed.
- [ ] Rollback procedure available.
- [ ] Version tag created.

Commands:

```bash
git tag -a v[VERSION] -m "Stable version [VERSION]"
git push origin v[VERSION]
```

## 2. Packaging

```bash
python -m build
```

Verification:

```bash
sha256sum dist/*
```

## 3. Deployment

| Step | Command / action | Status | Comment |
|---:|---|---|---|
| 1 | Backup | [ ] | [TO BE COMPLETED] |
| 2 | Deploy the tagged version | [ ] | [TO BE COMPLETED] |
| 3 | Verify the service | [ ] | [TO BE COMPLETED] |
| 4 | Check logs | [ ] | [TO BE COMPLETED] |
| 5 | Test the main command | [ ] | [TO BE COMPLETED] |
| 6 | Document the deployed version | [ ] | [TO BE COMPLETED] |

## 4. Post-deployment checks

```bash
systemctl status [SERVICE_NAME]
journalctl -u [SERVICE_NAME] -n 100 --no-pager
```

- [ ] The service is active.
- [ ] No critical error appears in the logs.
- [ ] The main command responds.
- [ ] The deployed version matches the validated tag.
- [ ] Rollback is documented and testable.

## Final validation

| Field | Value |
|---|---|
| Deployed version | [VERSION] |
| Production date | [YYYY-MM-DD] |
| Environment | [TO BE COMPLETED] |
| Owner | [NAME] |
| Rollback tested | [Yes / No] |
| Final status | [In production / Failure / Rollback] |

---

# Document change history

| Date | Version | Author | Change |
|---|---|---|---|
| [YYYY-MM-DD] | 0.1 | [NAME] | Template creation |
| [YYYY-MM-DD] | [VERSION] | [NAME] | [TO BE COMPLETED] |
