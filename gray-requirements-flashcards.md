# GRAY - Requirements — Flashcards

> 11 flashcards for the SWA Requirements topics.
> Each card: **Front** (topic + prompt) → **Back** (key points to recall).

---

## 1. Requirements Engineering General

**What are the core activities and principles of Requirements Engineering for a software architect?**

- **RE activities**: elicitation, documentation, validation, management
- **Kano model**: Basic (must-have), Performance (linear), Excitement (delight)
- **Requirements** describe WHAT the system must do, not HOW
- SWA must ensure requirements are **testable and traceable**
- **Stakeholder analysis** identifies who influences requirements
- Requirements evolve; **change management** process is essential

---

## 2. Problem vs Solution Space

**How do you distinguish the Problem Space from the Solution Space in requirements?**

- **Problem Space**: stakeholder needs, goals, and domain constraints
- **Solution Space**: technical design, architecture, implementation choices
- Mixing spaces leads to **premature design decisions** in requirements
- **Twin Peaks** model: requirements and architecture co-evolve iteratively
- SWA bridges both spaces via **ASR identification** and trade-off analysis
- Domain model belongs to **Problem Space**; deployment model to Solution Space

---

## 3. Classification of Requirements

**How are requirements classified into functional and non-functional categories?**

- **Functional**: what the system does (features, business rules, data)
- **Non-functional (quality)**: how well the system performs (ISO 25010)
- **Constraints**: mandatory boundaries (technology, legal, organizational)
- **ISO 25010** qualities: reliability, security, maintainability, performance, etc.
- NFRs are **architecturally significant** — they shape design decisions
- Each NFR needs a **measurable quality scenario** for testability

---

## 4. SWA Goals in Requirements Engineering

**What are the architect's specific goals and responsibilities in RE?**

- Identify **Architecturally Significant Requirements (ASR)** early
- Ensure NFRs are **specific, measurable, and testable** (quality scenarios)
- Challenge requirements that are **contradictory or technically infeasible**
- **Utility Tree** prioritizes ASRs by business value and architectural risk
- SWA participates in **requirements reviews** and validation workshops
- Bridge between **stakeholder needs** and **technical feasibility**

---

## 5. Requirement Elicitation

**What techniques are used to elicit requirements, and what are their trade-offs?**

- **Interviews**: deep insight but time-intensive and interviewer-biased
- **Workshops** (e.g., JAD): collaborative, fast consensus, but expensive to organize
- **Prototyping**: validates UI/UX early; risk of **anchoring** on prototype
- **Observation** (ethnography): reveals tacit knowledge users cannot articulate
- **Document analysis**: leverages existing specs but may be outdated
- **Questionnaires**: scalable for large groups but low-depth responses
- SWA focuses on eliciting **quality attributes and constraints**

---

## 6. Requirement Consolidation

**How are elicited requirements consolidated into a coherent, conflict-free set?**

- **Consolidation** merges, deduplicates, and resolves requirement conflicts
- **Conflict types**: contradictions, redundancies, ambiguities, gaps
- **Prioritization** techniques: MoSCoW, Kano, Weighted Scoring, Cost of Delay
- **Negotiation** with stakeholders when trade-offs are unavoidable
- **Traceability matrix** links requirements to sources and tests
- SWA ensures **architectural consistency** across consolidated requirements

---

## 7. Requirement Analysis

**How does requirement analysis ensure quality, feasibility, and architectural alignment?**

- **Analysis** checks completeness, consistency, feasibility, and testability
- **Impact analysis** evaluates how new requirements affect existing architecture
- **Feasibility study**: technical risk, cost, and timeline assessment
- **Modeling** techniques: use cases, user stories, domain models, state diagrams
- **Acceptance criteria** must be defined for every requirement
- SWA validates that NFRs are **architecturally achievable** with chosen tactics

---

## 8. Requirements Pyramid

**What is the Requirements Pyramid and how do abstraction levels relate?**

- **Pyramid levels**: Business Goals → Features → Use Cases → User Stories → Tasks
- Each level adds **detail and testability**; higher levels are more stable
- **Epics** decompose into stories; stories into **acceptance criteria**
- **INVEST** criteria for good user stories: Independent, Negotiable, Valuable, Estimable, Small, Testable
- SWA works primarily at **Feature and Use Case** levels for ASR identification
- **Vertical slicing** delivers value across all architecture layers per story

---

## 9. Definition of Done vs Definition of Ready

**How do DoD and DoR ensure quality gates in agile requirements management?**

- **DoR**: checklist before a story enters a sprint (clear, estimated, testable)
- **DoD**: checklist before a story is considered complete (coded, tested, reviewed)
- DoR prevents **incomplete requirements** from entering development
- DoD ensures **consistent quality** across all delivered increments
- SWA adds architectural criteria: **ADR written, NFRs validated, no new debt**
- Both evolve over time as the team **matures and learns**

---

## 10. FURPS+ and Non-Functional Requirements

**What is the FURPS+ model and how does it structure non-functional requirements?**

- **FURPS+**: Functionality, Usability, Reliability, Performance, Supportability
- **+** adds: Design, Implementation, Interface, Physical constraints
- Each quality must have **measurable acceptance criteria** (response time < 200ms)
- **Quality scenarios** (SEI format) make NFRs testable and unambiguous
- NFRs drive **architectural decisions** more than functional requirements
- Trade-offs between qualities require **explicit stakeholder agreement**

---

## 11. Role of SWA and Quality Attributes

**How does the software architect translate quality attributes into architectural decisions?**

- SWA is the **guardian of quality attributes** across the system lifecycle
- **ATAM** evaluates architecture against quality attribute scenarios
- **Sensitivity points**: decisions affecting one quality attribute significantly
- **Trade-off points**: decisions affecting multiple qualities in opposing directions
- **Risks** and **non-risks** documented for stakeholder transparency
- Quality attributes must be **prioritized** — you cannot optimize all equally

---
