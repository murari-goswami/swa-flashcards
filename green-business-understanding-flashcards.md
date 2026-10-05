# GREEN - Business Understanding — Flashcards

> 9 flashcards for the SWA Business topics.
> Each card: **Front** (topic + prompt) → **Back** (key points to recall).

---

## 1. Siemens Development System

**What is the Siemens Development System and how does it guide software development at Siemens?**

- **SDS** is Siemens' company-wide framework for product development
- Combines **agile methods** with stage-gate governance for enterprise scale
- **Quality Gates** (QG0–QG5) ensure milestone-based decision checkpoints
- Architects must align **architecture milestones** with QG deliverables
- **SWCOE** provides cross-BU standards, tools, and best practices
- SDS balances **local team autonomy** with corporate compliance needs

---

## 2. Cynefin Framework

**How does the Cynefin framework help architects choose the right approach for a given problem?**

- Five domains: **Clear, Complicated, Complex, Chaotic, Confused**
- **Clear**: best practice, sense-categorize-respond (standard patterns)
- **Complicated**: good practice, sense-analyze-respond (expert analysis)
- **Complex**: emergent practice, probe-sense-respond (experiments, spikes)
- **Chaotic**: novel practice, act-sense-respond (stabilize first)
- Architects use Cynefin to decide between **upfront design vs emergent architecture**

---

## 3. Output vs Outcome vs Impact

**What is the difference between Output, Outcome, and Impact, and why does it matter for architects?**

- **Output**: what we build (features, components, deliverables)
- **Outcome**: behavior change in users enabled by the output
- **Impact**: business-level result (revenue, market share, cost reduction)
- Teams often optimize for **output** when they should target **outcome**
- **OKRs** connect team objectives to measurable outcome/impact results
- Architects should justify decisions by **expected outcome**, not just technical merit

---

## 4. Technical Debt

**How should architects manage technical debt from a business perspective?**

- **Cunningham's metaphor**: debt = faster delivery now, interest = future cost
- **Quadrant**: Deliberate/Inadvertent × Prudent/Reckless (4 types)
- **Prudent deliberate**: conscious trade-off with documented repayment plan
- Debt becomes visible through **velocity decline and defect rate increase**
- Architect must **quantify debt in business terms** (cost, risk, timeline impact)
- **Boy Scout Rule**: leave code better than found; incremental payoff

---

## 5. Continuous Delivery and DORA Metrics

**How do DORA metrics measure software delivery performance, and what enables Continuous Delivery?**

- Four DORA metrics: **Lead Time, Deploy Frequency, MTTR, Change Failure Rate**
- **Elite performers**: multiple deploys/day, <1h lead time, <1h MTTR
- **CD pipeline**: commit → build → test → staging → production (automated)
- Architecture must support **independent deployability** and feature toggles
- **Trunk-based development** with short-lived branches reduces merge conflicts
- DORA proves **speed and stability are not trade-offs** — they reinforce each other

---

## 6. Component Teams vs Feature Teams

**What are the trade-offs between component teams and feature teams?**

- **Component teams**: own a technical layer (DB, API, UI); deep expertise
- **Feature teams**: own end-to-end delivery of a user-facing feature
- Component teams create **handoff bottlenecks** and cross-team dependencies
- Feature teams need **broad skills** but deliver value faster with less coordination
- **Conway's Law**: architecture mirrors team structure; choose teams intentionally
- Hybrid approach: feature teams with **enabling teams** for specialized expertise

---

## 7. Host Leadership

**What is Host Leadership and how does it apply to software architects?**

- **Host metaphor**: leader as host of a party, not commander of troops
- Four positions: **In the Spotlight, With the Guests, In the Gallery, In the Kitchen**
- **Spotlight**: set direction and vision; **Gallery**: observe and reflect
- **With Guests**: collaborate as equal; **Kitchen**: prepare behind scenes
- Architects shift between **leading and stepping back** depending on context
- Effective architects **create space** for teams to make decisions autonomously

---

## 8. Open Source Software at Siemens

**What are the key considerations for using and contributing to OSS at Siemens?**

- **License compliance**: permissive (MIT, Apache) vs copyleft (GPL, AGPL)
- **AGPL** requires source disclosure for network use — high risk for products
- Siemens uses **OSS scanning tools** to detect license and vulnerability issues
- **Inner Source**: applying OSS collaboration patterns within the company
- Architects must evaluate **community health, maintenance, and security** of OSS
- **SBOM** (Software Bill of Materials) tracks all OSS components in products

---

## 9. 97 Things Every SWA Should Know

**What are the key recurring themes from '97 Things Every Software Architect Should Know'?**

- **Simplicity**: prefer the simplest solution that could possibly work
- **Communication** is more important than technical skill for architects
- **There is no one-size-fits-all** solution; context drives every decision
- **Continuously learn**: architects must stay hands-on and current
- **Stand behind decisions** and own consequences; avoid ivory tower
- Architecture is about **trade-offs**, not finding the perfect answer

---
