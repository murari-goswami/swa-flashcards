# BLUE - Architecture — Flashcards

> 11 flashcards for the SWA Architecture topics.
> Each card: **Front** (topic + prompt) → **Back** (key points to recall).

---

## 1. Goals-Principles-Decisions (GPD) Model

**What is the GPD chain and how does it connect requirements to implementation?**

- **GPD** cascades: Requirement → Goal → Principle → Decision
- **Goals**: what to achieve (consistency, usability, reusability)
- **Principles**: general rules and boundaries derived from goals
- **Decisions**: specific implementation steps fulfilling a principle
- Ensures **traceability** — decisions traced back through principle to goal
- Challenges discussed **at the principle level**, decisions re-opened without touching goals
- **Freedom of Choice**: decisions can change while goals and principles remain stable

---

## 2. Architecture Decision Records (ADR)

**What are ADRs, their templates, and how do they prevent architectural amnesia?**

- **5 intro questions**: What, How, Where, How much, Difficulties
- **Nygard (2011)** format: Title, Context, Decision, Status, Consequences
- **MADR** adds Considered Options, Pros/Cons, and **Decision Drivers**
- **Decision Drivers** are the **hinge** — turn opinion into traceable evaluation
- Statuses: **Proposed, Accepted, Rejected, Deprecated, Superseded**
- SWA duties: document decisions, ensure consistency, regular review, define process
- **Docs-as-Code**: ADRs in repo, PR = review, merge = approval
- **Fitness Functions**: validate code against ADRs, report violations automatically

---

## 3. Architecture Documentation

**How do we define, view, and document software architecture?**

- **IEEE 1471**: components, relationships, environment, governing principles
- **Booch**: significant decisions measured by **cost of change**
- **Johnson**: architecture is about the important stuff, whatever that is
- **4+1 Views**: Use Case, Logical, Process, Development, Physical (+n extra)
- **C4 Model**: Context (mgmt), Container (architects/DevOps), Component (dev), Code (dev)
- **arc42** template: do not delete any part; risk: incomplete or overloaded
- **Drawing tools** (Visio, PlantUML): lightweight; **Modelling tools** (MagicDraw): consistency
- SWA duties: define needed views, keep views consistent, document decisions, review regularly

---

## 4. Systematic Architecture Design

**How does the L-Model guide systematic architecture from forces to implementation?**

- Architecture = **Forces + Creativity + Communication + Decisions**
- **Forces** = Requirements (functional + quality) + Constraints (infra + non-technical)
- **ASR** found via **"5 miles wide, 5 inches deep"** — shallow scan, then deep dive
- **L-Model**: vertical (elicitation → domain → dynamics → scope) then horizontal (design → deploy → principles → increments)
- Maturity: **Draft → Walking Skeleton → MVP → MMP/MLP**; Skeleton = end-to-end production quality
- **Inverse Conway**: design target architecture first, reshape teams to match
- **Pyramid**: max 3 levels (System → Subsystem → Component) + cross-cutting concerns
- **Strategic** = system-wide decisions; **Tactical** = component-level decisions
- Entire **L-Model traversed every iteration**; empty phases become no-op, never skipped

---

## 5. Quality Scenarios and Design Tactics

**How do Quality Scenarios drive tactic selection and trade-off management?**

- Quality Scenario has **6 elements**: Source, Stimulus, Artifact, Environment, Response, Response Measure
- **Utility Tree**: Root (utility) → Quality Domains → Refinements → Leaf scenarios
- Each leaf rated on **Business Value** and **Architectural Impact**; **H/H = ASR**
- **Fault Tolerance** tactics: detection (heartbeat), redundancy, rollback, transactions
- **Security** tactics: authenticate/authorize, intrusion detection, audit trail
- **Performance** tactics: manage event rate, concurrency, scheduling policy
- **Modifiability** tactics: semantic coherence, hide information, intermediary, polymorphism
- **Design Tactic** = single building block; **Design Strategy** = overall plan combining tactics
- Trade-off management: improving one quality often degrades another (e.g., security vs performance)

---

## 6. Architectural and Design Patterns

**How are patterns selected, ordered, and what are their key trade-offs?**

- **Pattern Language** template: problem/context, solution, behavior, consequences (trade-offs)
- **5-step selection**: identify problem → check catalog → analyze benefits → analyze liabilities → pick simplest
- Order: **Quality Scenarios → Tactics → Patterns LAST** (patterns implement tactics)
- **Layered**: separation of concerns; liability = **sinkhole anti-pattern**, lower performance
- **Event-Driven**: extreme decoupling + scalability; liability = **traceability** and debugging difficulty
- **Pipes & Filters**: chainable transforms; liability = **not suitable for UI**, parse/serialize overhead
- **Microservices**: independent deploy + scaling; liability = **distributed transactions**, monitoring complexity
- **Strangler**: gradual monolith migration via facade routing to new services
- **Hexagonal** (Ports & Adapters): uses **Adapter pattern + Dependency Injection**; flexible but more indirection

---

## 7. Domain-Driven Design (DDD)

**What are the strategic and tactical building blocks of DDD?**

- **Ubiquitous Language**: shared strict language in code, diagrams, speech
- **Bounded Contexts**: models valid only within a specific context boundary
- 3 **Subdomains**: **Core** (full DDD), **Supporting** (simple), **Generic** (buy)
- **Context Map** patterns: **Shared Kernel**, **Conformist**, **Anti-corruption Layer (ACL)**
- **Event Storming** colors: orange=Event, blue=Command, yellow=Actor, purple=Policy
- Tactical: **Entity** (identity+lifecycle), **Value Object** (immutable, no identity)
- **Aggregate** (consistency boundary via Root), **Repository**, **Factory**
- **Anemic model** = anti-pattern; **Rich model** encapsulates domain behavior
- **Domain Layer** depends on nothing; Infrastructure implements domain interfaces
- **Conway's Law**: team structure mirrors Bounded Context boundaries

---

## 8. Architecture in Agile Environment

**How is architecture managed within agile development practices?**

- **Architectural Runway**: architecture leads development by 1-2 sprints ahead
- 4 **Enablers**: Exploration, Architectural, Infrastructure, Compliance
- NFR types: **Story-like** (deliver in sprint), **Constraining** (acceptance criteria), **Cross-cutting** (spike+DoD)
- **DoD for Architecture**: done, documented (ADR), communicated, validated (PoC)
- **Architecture Owner**: part-time team representative, codes and communicates
- **Tiger Teams** conquer first; **Travellers** rotate between teams spreading know-how
- **Simplicity before generality**; hard-coded over excessive configuration
- Architecture smells: too much abstraction, futuristic design, paper architecture
- Decide at **last reasonable moment**: max knowledge, no team blocking
- **Spikes**: research tasks where goal is learning, not delivery

---

## 9. Architecture Refactoring

**How do you manage architectural refactoring and technical debt?**

- **Lehman's 2nd Law**: system complexity grows naturally, causing design erosion
- Smells: **External** (failing builds, slow deploy) vs **Internal** (cyclic deps, duplication)
- 4 levels: **Class** (developer/task) → **Component** (team/backlog) → **Subsystem** (epic) → **System** (project/CTO)
- **Reengineering** = reverse + forward engineering; **Rewriting** = discard and rebuild
- **Tech Debt Quadrant**: Deliberate/Inadvertent × Prudent/Reckless (4 quadrants)
- Financial metaphor: **loan** (quick delivery), **interest** (costly maintenance), **repayment** (refactor)
- 6 steps: root cause → changes → **Business Case** (ROI) → present → plan → schedule
- **Corridors**: reserved capacity (e.g. 15% per sprint) for maintenance
- **Triggers**: automatic response when metrics exceed limits (e.g. Sonar red)
- Measure debt: static analysis, velocity drops, change density in components

---

## 10. Experience — Architecture

**What cross-cutting lessons emerge from real-world architecture examples?**

- **Make the invisible visible**: latency diagram, ADR index, dependency cycle
- **Short-term workaround + documented repayment** is prudent, not sloppy
- **Decide against drivers, not opinions**: GPD and MADR enable principled re-opening
- **Bound what grows**: Claim-Check and latency budgets cap scaling dimensions
- **Architecture is a social activity**: PO, PM, domain experts appear everywhere
- Non-technical forces can **defeat technically correct architecture** (adoption, trust)
- Walking Skeleton cheapest risk reducer **before product-market fit**

---

## 11. Systematic Architecture Design

**How does the L-model drive systematic architecture from forces to implementation?**

- Architecture = **Forces + Creativity + Communication + Decisions**
- **Forces = Requirements + Constraints**; constraints include non-technical ones
- **ASR** identified via **5 miles wide, 5 inches deep** method
- **L-model**: vertical (elicit, domain, dynamics, scope) then horizontal (design to increments)
- Maturity: **Initial Draft → Walking Skeleton → MVP → MMP/MLP**
- **Pyramid model**: max 3 levels (System → Subsystem → Component) + cross-cutting
- **Inverse Conway Maneuver**: design architecture first, then reorganize teams to match

---
