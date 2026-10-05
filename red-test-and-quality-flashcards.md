# RED - Test & Quality — Flashcards

> 14 flashcards for the SWA Test & Quality topics.
> Each card: **Front** (topic + prompt) → **Back** (key points to recall).

---

## 1. Value of Testing, Test Exit Criteria

**What determines when testing should stop, and how does the Cost of Quality model guide testing investment?**

- **Cost of Quality** = prevention + appraisal + failure costs
- Sweet spot: marginal cost of next bug exceeds **expected loss**
- **Test exit criteria** define conditions to end a testing phase
- Testing provides **information** about quality, not quality itself
- **Residual risk** remains after testing; must be communicated to stakeholders
- **Absence-of-errors fallacy**: bug-free software can still fail users

---

## 2. Software Testing and Quality

**How do QA, QC, and Testing differ, and what are the seven principles of software testing?**

- **QA** = process-focused prevention; **QC** = product conformity checks
- **Verification** (building product right) vs **Validation** (building right product)
- Seven principles include **defect clustering** and **pesticide paradox**
- **Exhaustive testing** is impossible; use risk-based prioritization
- **Design for Testability** uses DI and Humble Object patterns
- **Test strategy** is static/high-level; **test plan** is project-specific
- Testability is a key **non-functional requirement** for architecture

---

## 3. Test Levels, Test Pyramid

**What are the four test levels, and how do the Testing Pyramid and Testing Trophy differ in strategy?**

- Four levels: **Unit, Integration, System, Acceptance** testing
- **Testing Pyramid** (Cohn): broad unit base, narrow E2E top
- **Testing Trophy** (Dodds): emphasizes integration + static analysis
- **Ice Cream Cone** anti-pattern inverts pyramid with excessive E2E
- **Shift-left** finds defects early at lowest, cheapest test level
- Architecture must support **isolation and DI** to fill pyramid base

---

## 4. Unit Testing

**What defines a good unit test, and how do test doubles, coverage metrics, and TDD support unit-level verification?**

- **SUT/CUT**: smallest independently testable code element in isolation
- Test doubles: **Stub, Mock, Spy, Fake, Dummy** replace dependencies
- Structural coverage: **Statement, Branch, MC/DC** (ASIL D requires MC/DC)
- **TDD Red-Green-Refactor** drives design and ensures early coverage
- **Over-mocking** couples tests to implementation, breaking on refactor
- **Host vs Target**: fast CI feedback vs real compiler/HW fidelity
- **Humble Object** separates testable logic from untestable environment

---

## 5. Integration Testing

**What integration strategies exist, and how does integration testing verify component interactions?**

- Strategies: **Top-Down, Bottom-Up, Sandwich, Big-Bang** integration
- **Test Driver** calls SUT from above; **Test Stub** replaces below
- **HSI testing** verifies hardware-software interface correctness
- **Contract Testing / CDC** validates interface compatibility independently
- Resource allocation testing checks **RAM, ROM, Stack, CPU** usage
- **Fault injection** verifies error handling and recovery mechanisms
- **Bidirectional traceability** (SRTM) links requirements to test cases

---

## 6. Contract Testing

**How do Consumer-Driven Contracts prevent integration failures in distributed systems?**

- **CDC**: consumer defines expected provider behavior in a contract
- **Pact framework** generates pact files from consumer test expectations
- **Mock drift** problem: local mocks diverge from real provider behavior
- **Provider States** set up required preconditions for contract verification
- **Pact Broker** shares and versions contracts across CI/CD pipelines
- Contracts verify **interface compatibility**, not business logic
- Enables **independent deployability** of services without full E2E tests

---

## 7. Systematic Test Design

**What is the systematic test design process, and how do black-box and white-box techniques complement each other?**

- **Test basis**: requirements, architecture, specs drive test derivation
- Black-box: **Equivalence Partitioning, BVA, State-based** testing
- White-box: **Statement, Branch, Path** coverage of code structure
- **Test oracle** defines expected results for pass/fail evaluation
- **SRTM** traces requirements to test cases bidirectionally
- STD is a **process/methodology**; TDT are architectural design patterns

---

## 8. Test Design Tactics

**How do Test Design Tactics translate a test strategy into specific, measurable test cases?**

- **TDT** reduce infinite input space to optimal finite test scenarios
- **EP** divides domain into valid/invalid equivalence classes
- **BVA** tests boundary values B, B-delta, B+delta for off-by-one errors
- **Decision tables** expose missing or contradictory requirement rules
- **State transition** testing: 0-switch (states) vs 1-switch (sequences)
- **MC/DC** required for safety-critical code (ASIL D / ISO 26262)
- Architecture needs **controllability and observability** to apply TDT

---

## 9. Test-Driven Development (TDD)

**Why is TDD considered a design technique rather than just a testing method?**

- **Red-Green-Refactor**: fail test, minimal code, clean up duplication
- TDD is primarily **analysis and design** (Test-Driven Design), not just QA
- Enforces **SOLID principles**, DI, low coupling, and high cohesion
- **Sociable** (Detroit) tests real collaborators; **Solitary** (London) mocks all
- Tests serve as **living executable documentation** of API behavior
- TDD alone cannot cover **NFRs**: performance, concurrency, safety

---

## 10. Behavior Driven Development (BDD)

**How does BDD bridge the communication gap between business and technical teams through executable specifications?**

- Uses **Gherkin** format: Given (context), When (action), Then (result)
- **Three Amigos**: BA + Developer + Tester align on examples before coding
- **Outside-In** development drives architecture from acceptance criteria inward
- **Living Documentation** auto-generated from CI test execution results
- **Declarative** scenarios describe business intent, not UI click steps
- Requires **layered/hexagonal architecture** to isolate tests from infrastructure

---

## 11. Risk Based Testing

**How does Risk-Based Testing prioritize testing effort using risk assessment?**

- Risk = **Likelihood x Impact**; prioritizes where failure hurts most
- **Product risk** (quality) is mitigable by testing; **project risk** is not
- **RPN** (Risk Priority Number) ranks risks by probability, impact, detectability
- **FMEA** for safety-critical; **PRAM** for lightweight risk analysis
- **Depth-first** targets high-risk items; **Breadth-first** covers all areas
- Risk register must be **continuously updated**, not frozen after kick-off
- **3 Amigos** bring business, dev, and QA perspectives to risk assessment

---

## 12. Testing Non-Functional Requirements (NFR Testing)

**How are quality attributes specified, measured, and tested across architecture and test levels?**

- NFR testing verifies **how well** a system performs, not what it does
- **Quality Attribute Scenario**: 6-part format with measurable response metric
- **Utility Tree** prioritizes NFRs by business value and architectural risk
- **FURPS+** model: Functionality, Usability, Reliability, Performance, Supportability
- **Fault Injection** deliberately introduces faults to verify safety mechanisms
- Quality cannot be **tested in**; testing only verifies architectural decisions
- **Shift-left NFR**: test reliability and performance early, not only at end

---

## 13. Design for Testability

**What architectural tactics make software testable, and what are the key trade-offs?**

- Two pillars: **Controllability** (set inputs/states) and **Observability** (monitor outputs)
- **Humble Object** extracts testable logic from untestable framework code
- **Dependency Injection** enables test doubles and component isolation
- **Front-door** tests public API; **back-door** uses testability interfaces
- Trade-offs: testability vs **encapsulation, performance, and security**
- James Bach's 5 dimensions: intrinsic, epistemic, project, subjective, value
- DFT can save up to **10% of total project budget** through early defect detection

---

## 14. Internal Software Quality

**How does internal software quality relate to testability, and what are the three levels of code quality?**

- **Internal quality** = static code/architecture properties (ISO 9126/25010)
- Three levels: **Micro** (lines), **Macro** (classes/SOLID), **Architecture** (layers/cycles)
- **Quality Management Chain**: Process -> Internal -> External -> Quality-in-Use
- **CQM**: static analysis, coding guidelines, metrics, peer reviews
- **Defect Gap Analysis** tracks phase gap between error introduction and detection
- Quality cannot be **tested in**; development and architecture create quality
- Architect acts as **protector of internal quality** across all three levels

---
