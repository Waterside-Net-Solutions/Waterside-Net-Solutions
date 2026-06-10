# Coordination Control Loop Framework (CCL-F)

### Canonical Framework Document

**Author:** Morgan Landry
**Affiliation:** Waterside Net Solutions | CCL-F Project
**Version:** 0.1 — June 2026
**Status:** Working paper — subject to revision
**Cite as:** Landry, M. (2026). *Coordination Control Loop Framework (CCL-F)*, Version 0.1. Waterside Net Solutions.
**License:** CC BY-NC-ND 4.0
**Intended audience:** Safety engineers, organizational systems researchers, and AI governance practitioners.

-----

## Contents

- [Executive Summary](#executive-summary)
- [Overview](#overview)
- [The CCL-F Layer Stack](#the-ccl-f-layer-stack)
- [Layer 0 — The Architecture Precondition](#layer-0--the-architecture-precondition)
- [Layer 1 — Rules 1-9](#layer-1--rules-1-9)
- [Layer 2 — Coordination Evaluation Semantics](#layer-2--coordination-evaluation-semantics)
  - Closure Quality
  - Evidence Novelty Requirement
  - Ambiguity Debt
  - Reversibility Logic
  - Escalation Conditions
  - Loop Exit Taxonomy
- [Layer 3 — Coordination Dynamics](#layer-3--coordination-dynamics)
  - Distributed Closure Constraint
  - Loop Tractability Assessment
  - Coordination Trajectory
  - Revision Rigidity and Trajectory Lock
  - Loop Entanglement
  - Closure-Resistant Loop
- [Layer 4 — Runtime Realization](#layer-4--runtime-realization)
- [Failure Taxonomy Across Historical and Emerging Cases](#failure-taxonomy-across-historical-and-emerging-cases)
- [Validation and the Selection Problem](#validation-and-the-selection-problem)
- [Relationship to STAMP/STPA](#relationship-to-stampstpa)
- [Key Definitions](#key-definitions)
- [The Central Claims](#the-central-claims)
- [AI Applications](#ai-applications)
- [Status and Next Steps](#status-and-next-steps)
- [References](#references)
- [Changelog](#changelog)

-----

## Executive Summary

When the Space Shuttle Challenger broke apart seventy-three seconds after launch, the engineers who had warned against flying already knew what had gone wrong. Their signal had entered the organizational system, been processed, and failed to survive it. The knowledge existed. The loop never closed.

The Coordination Control Loop Framework (CCL-F) is a formal model of why this happens — and how to detect it before the disaster rather than explain it afterward. It operates at the commitment layer: the organizational process by which known safety signals are either converted into executable decisions or lost. Existing safety frameworks, including Leveson’s STAMP, identify what constraints must exist and model how their absence causes accidents [1]. CCL-F addresses the prior question: whether the organizational architecture is capable of enforcing constraints it already knows about. Put directly: STAMP identifies what safety constraints must be enforced. CCL-F tracks whether the organizational commitment process actually enforces them.

The framework distinguishes two failure conditions that current safety theory treats as one. Coordination failure occurs when a loop exists but fails to close — the signal is present, the architecture is intact, but the process breaks down. Coordination non-instantiation occurs when no valid loop exists to fail — the architecture itself was never built. The Architecture Precondition formalizes this second condition: the architectural prerequisites of stewardship, channel integrity, and boundary coherence that must be in place before any coordination evaluation is meaningful.

These ideas have direct application beyond aerospace. The same failure modes appear in disaster response, regulatory systems, and — with increasing urgency — in the deployment of AI agents in high-consequence environments [16][17].

The framework’s deepest claim is this: a coordination system becomes dangerous when its mechanisms for preserving coherence overpower its mechanisms for revision. Coherence is healthy only when it remains corrigible.

-----

## Overview

Most organizational disasters share a quiet precondition: the relevant information already existed inside the system. The Challenger engineers knew. The Columbia damage assessment team knew. The Katrina flood planners knew. What failed in each case was not knowledge — it was the organizational process that should have converted knowledge into action.

CCL-F is a formal model of that process. It focuses on the commitment layer — the space between signal and decision — and asks a specific question: did this safety-relevant input actually close before irreversible execution began, or was it compressed, overridden, or administratively dissolved?

The framework organizes its analysis across five layers, from the architectural preconditions that make coordination possible, through the operational rules that govern how loops are managed, to the evaluation semantics that determine whether a loop is genuinely closed, to the dynamics that govern whether closure is achievable and where the system is heading, to the runtime systems that monitor all of this in real time.

**Scope boundary.** A coordination loop in CCL-F is not a metaphor for any process involving feedback or interaction. It is a specific organizational structure: a safety-relevant signal that has entered a formal commitment process, requires evidence-based closure, and carries defined consequences for irreversible execution if left open. The framework’s explanatory power depends on maintaining this specificity. CCL-F does not model feelings, interpersonal dynamics, cultural processes, or generalized information flows — except insofar as these produce or suppress coordination signals that enter the commitment process. Where they do, they are in scope. Where they don’t, they aren’t.

-----

## The CCL-F Layer Stack

CCL-F’s five layers are logically dependent. A failure at any layer renders all lower layers indeterminate — you cannot evaluate operational coordination in a system whose architecture doesn’t exist, and you cannot trust a runtime monitor if the evaluation semantics and dynamics it applies are unsound.

```
LAYER 0 - ARCHITECTURE VALIDITY
  The Architecture Precondition
  Stewardship completeness, Channel integrity, Boundary coherence
  Failure: coordination non-instantiation
  Effect: Layers 1-4 unevaluable

LAYER 1 - COORDINATION OPERATION
  Rules 1-9
  Visibility, Classification, Interpretive Stability
  Ownership, Authority, Reversibility
  Recurrence, Structural Updating, Distribution
  Failure: coordination failure
  Effect: loops open under execution conditions

LAYER 2 - COORDINATION EVALUATION SEMANTICS
  Closure quality, Evidence thresholds
  Ambiguity debt, Reversibility logic, Escalation conditions
  Loop Exit Taxonomy (14 exit types)
  Failure: false closure / administrative compression
  Effect: open loops recorded as closed

LAYER 3 - COORDINATION DYNAMICS
  Distributed Closure Constraint, Loop Tractability Assessment
  Coordination Trajectory
  Revision Rigidity, Trajectory Lock
  Loop Entanglement, Closure-Resistant Loop
  Failure: trajectory lock / unbounded convergence / unregistered entanglement
  Effect: system loses revision capacity before execution

LAYER 4 - RUNTIME / SOFTWARE REALIZATION
  Commitment state machine, Observability
  Telemetry ingestion, Execution gating
  Digital twin simulation, Coherence scoring, Audit trail
  Failure: runtime degradation
  Effect: real-time coordination state untrackable
```

-----

## Layer 0 — The Architecture Precondition

### The Problem This Condition Solves

Rules 1 through 9 describe how organizations manage coordination loops once those loops exist. But some catastrophic failures happen earlier — not because the loops failed, but because no coherent loop architecture was ever built. Nobody owned the failure mode. The signal channel collapsed under the exact conditions it was needed. Organizations that assumed they were coordinating turned out to have been assuming coordination rather than practicing it.

The Architecture Precondition formalizes this prior condition. Before asking whether a loop closed, ask whether it could have closed at all.

### Statement

Before any irreversible high-consequence execution, the coordination architecture governing that execution must be explicitly registered, verified, and boundary-coherent. A coordination architecture is the set of stewardship assignments, signal channels, and inter-organizational boundary agreements that make Layers 1 through 4 operationally meaningful. Where this architecture is absent, incomplete, or boundary-incoherent, no evaluation of Rules 1 through 9 is valid — because the infrastructure those rules presuppose does not exist.

### Canonical Definition: Architecture Void

> An architecture void exists when coordination-critical stewardship, signal pathways, or inter-organizational boundary agreements are absent, unverified, or structurally incoherent, rendering coordination loops non-closable under execution conditions.

### The Three Sub-Conditions

The Architecture Precondition is satisfied if and only if all three of the following hold:

**AP.1 — Stewardship Completeness**

For every identified high-consequence failure mode, a named agent or organizational unit has explicitly accepted closure responsibility. Nominal or assumed ownership does not satisfy this condition. The acceptance must be registered, documented, and traceable. “Everyone is responsible” means no one is.

AP.1 has two components that must both be satisfied:

**AP.1a — Active Stewardship.** A named steward has explicitly accepted closure responsibility and is currently capable of exercising it. A steward who has been removed, has departed, or has been incapacitated without a registered successor produces an immediate stewardship void regardless of how complete the original assignment was.

**AP.1b — Stewardship Succession.** For every high-consequence failure mode, a named successor is registered in advance. A single named steward with no registered successor is a single point of failure in the coordination architecture. Stewardship succession is a formal precondition, not an afterthought — its absence means the Architecture Precondition is satisfied only until the steward becomes unavailable.

*Terminology note: CCL-F uses steward rather than owner to emphasize that closure responsibility is an accepted obligation rather than a property right. In STAMP, ITIL, ISO risk frameworks, and most aerospace governance documentation, the equivalent term is owner. The concepts are functionally equivalent; the distinction is intentional.*

**AP.2 — Channel Integrity**

Signal pathways from operational ground level to decision authority are explicitly registered, tested under realistic conditions, and confirmed functional before irreversible execution windows open. Channels that work under normal conditions but degrade under the conditions that actually matter — a storm, a launch emergency, a certification crisis — must have registered contingency pathways. Untested channels are treated as absent.

This sub-condition explains a recurring feature of post-mortems: investigators routinely discover that nobody knew who owned the signal, where it should have gone, or which organization held closure authority. The system appeared unified from the outside. It was never unified at all [4][5].

**AP.3 — Boundary Coherence**

In multi-organization systems, the coordination architecture must include explicit agreements specifying which organization owns each loop at each execution phase, how signals cross organizational boundaries, and what happens when boundary-crossing signals are contested or lost. Assumed boundary coherence does not satisfy this condition. Agreement must be registered and accepted by all parties.

### The Three Void Types

When The Architecture Precondition fails, it fails in one of three ways:

**AP-A: Stewardship Void** — No named agent has explicitly accepted closure responsibility for a high-consequence failure mode. Ownership is diffused, assumed, or contested — which under execution conditions is functionally equivalent to absent.

**AP-B: Channel Collapse** — Signal pathways exist under normal conditions but degrade under execution conditions, with no registered contingency. Observability fails precisely when it is most needed.

**AP-C: Boundary Incoherence** — Organizations that are individually coherent fail to compose into a coherent coordination architecture because their boundary agreements were assumed rather than negotiated. Internally rational systems produce irrational outcomes at the seams.

### Why This Matters

|Condition       |R1-R9      |Coherence    |Execution gates  |
|----------------|-----------|-------------|-----------------|
|AP satisfied    |Evaluable  |Assessable   |Meaningful       |
|AP not satisfied|Unevaluable|Indeterminate|Structurally void|


> *“When the Architecture Precondition fails, the architecture itself is the open loop.”*

-----

## Layer 1 — Rules 1-9

The nine operational rules describe what coordination integrity requires once a valid architecture exists. Each rule names a coordination property that must hold, the failure mode that occurs when it doesn’t, and the organizational correction that restores it.

The rules are ordered by constraint level: higher-order rules establish the conditions that lower-order rules operate within. Rules 1-3 establish the epistemic foundation — signals must be visible before they can be classified, and classification must stabilize before execution proceeds. Rules 4-6 govern ownership and decision architecture. Rules 7-9 govern systemic learning, structural updating, and the distribution of authority that makes updates real rather than nominal.

-----

### Rule 1: Signals Needed for Responsible Action Are Visible

**What it requires:** Safety-relevant signals must remain operationally visible through the full commitment process. A signal that is technically present but organizationally invisible has failed this rule.

**How it fails:** Signals lose operational weight without being formally removed. Rhetorical pressure, institutional momentum, and role dynamics dilute a signal’s standing until it is present in the record but absent from the decision [9].

CCL-F recognizes six signal types: constraint, uncertainty, anomaly, dissent, classification, and framing. The last type deserves particular attention. A framing signal is one whose content is an interpretive context rather than a technical constraint — its function is to shift how other signals are understood. When a framing signal achieves frame adoption without resolving the technical signals it reframes, technically present signals lose operational weight without being formally closed. This is how “prove it’s unsafe” replaced “prove it’s safe” at Challenger — not by overriding the engineering data, but by reframing the burden of proof so that the data no longer registered as sufficient.

**Why it matters:** Signal visibility is the epistemic foundation of the entire framework. Classification, interpretive stability, ownership, and authority are all meaningless if the signals those processes operate on have already lost organizational standing. A signal suppressed before it can be classified cannot be owned, stabilized, or closed — it simply disappears from the system while the hazard it names remains real.

**What to do:** Preserve raw engineering dissent and uncertainty through the full commitment process. Track whether a framing signal has displaced a technical signal’s standing, and flag this as a suppression event.

**Cases:** After Columbia’s launch, engineer Rodney Rocha’s concern about foam strike damage was present in the record but lost organizational standing under institutional pressure to treat the mission as normal [4]. During Katrina, ground-level signals about conditions in New Orleans were real and observable at street level — but the signal infrastructure between operational ground truth and federal decision-makers collapsed the moment it was most needed [8].

-----

### Rule 2: Classification Precedes Action

**What it requires:** Every execution-class decision requires explicit operational state classification. Unvalidated conditions cannot be classified as nominal.

**How it fails:** “Outside validated parameters” gets treated as “acceptable operational variation.” The classification error is quiet and consequential — it doesn’t block the process, it corrupts it. Every downstream decision inherits a false premise.

**Why it matters:** Classification determines which rules apply and what closure quality is required. A misclassified system state is not just an error — it is a systematically wrong input to every subsequent coordination decision. Organizations that classify off-envelope conditions as nominal don’t just make one bad call; they build an entire decision chain on a false foundation.

**What to do:** Before any execution authorization, the system must explicitly answer: what operational state are we in? CCL-F defines five operational states — nominal, elevated uncertainty, off-envelope, experimental, and containment — each with distinct coordination consequences. See Key Definitions for full definitions. Classification must be supported by evidence, not assumed. Unvalidated conditions cannot be classified as nominal.

**Cases:** Challenger’s launch state was classified as nominal despite O-ring temperatures below anything in the validated test data [5][6]. MCAS was classified as a minor stability enhancement — a classification that avoided the certification burden a novel flight-critical system would have triggered [7]. In both cases, the misclassification wasn’t accidental. It was convenient.

-----

### Rule 3: Interpretive Stability Precedes Execution

**What it requires:** Execution cannot proceed while interpretive uncertainty remains unresolved and unstabilized. This rule does not assume prior clarity — it requires that uncertainty be explicitly named, classified, and held stable before irreversible action proceeds.

**How it fails:** Organizations move toward execution while key questions remain open — not hiding the uncertainty, but compressing it. “Probably okay” becomes operationally equivalent to “okay.” The ambiguity doesn’t disappear; it gets buried under momentum. The failure is not ignorance — it is the refusal to formally acknowledge what is not yet known.

**Why it matters:** Unresolved ambiguity is not a neutral condition — it is an open coordination loop. Every decision made downstream inherits it. Unlike Rule 2 which governs how signals are classified, Rule 3 governs whether the interpretive state produced by that classification has stabilized sufficiently to support action.

**What to do:** Before execution, explicitly register what is known, what is assumed, and what remains genuinely uncertain. Do not compress uncertainty into a false resolution. Interpretive stability is achieved by naming the uncertainty, not by eliminating it.

**Cases:** Before Challenger launched, no one had validated O-ring performance at the forecast temperature. The uncertainty was real, acknowledged in engineering discussions, and then compressed into a launch authorization without ever stabilizing [5][6]. Boeing’s MCAS system behaved differently in different internal documents — the interpretive instability was never resolved before the aircraft entered service and killed 346 people [7].

-----

### Rule 4: Decisions Have Living Ownership

**What it requires:** Every decision has a named, accepting steward. Diffused ownership is functionally equivalent to no ownership.

**How it fails:** Ownership drifts across agencies, roles, and institutional momentum. No one person accepts the decision as theirs. Collective momentum carries the organization forward without clean accountability — everyone contributed, which means no one is responsible.

**Why it matters:** A decision without a named steward cannot be closed, only accumulated. The absence of ownership is itself a coordination failure.

**What to do:** Before any execution-class decision, a single agent must explicitly accept authorization, risk acceptance, and rationale documentation as their responsibility.

**Cases:** The Challenger launch decision was owned collectively by NASA and Thiokol management, engineering teams, and schedule pressure simultaneously — which meant it was owned by no one cleanly [5][6]. In the Katrina response, no single agency had explicitly accepted ownership of the catastrophic flood response loop. FEMA, DHS, Louisiana, and New Orleans each carried partial assumptions that had never been reconciled into actual stewardship [8].

-----

### Rule 5: Responsibility Matches Authority and Capacity

**What it requires:** The agents who bear failure responsibility must possess commensurate decision authority. This requirement has two dimensions — a static condition that must hold at any given moment, and a dynamic condition that must hold across time.

**R5.1 — Static Matching**

At any execution-class decision point, responsibility and authority must be explicitly matched and registered. An agent who bears failure responsibility without possessing decision authority is structurally prevented from preventing the failure they are accountable for. This is not a fairness issue — it is a coordination architecture failure. When the people most capable of preventing a failure are structurally prevented from doing so, the organization has designed itself to fail.

**R5.2 — Dynamic Co-evolution**

Over the lifecycle of a program, responsibility, authority, and benefits must co-evolve. When any of the three drifts relative to the others without explicit registration and correction, a coordination asymmetry accumulates. Three drift patterns are particularly dangerous:

- **Responsibility without authority drift** — as a program matures, operational responsibility concentrates at lower levels while authorization authority remains centralized. The people closest to the failure mode acquire the most accountability and the least power.
- **Benefits without accountability drift** — financial, reputational, or institutional benefits decouple from failure responsibility. Agents who capture the benefits of a decision bear none of its risk. This produces systematic incentive to compress uncertainty, misclassify operational states, and close loops by authority rather than evidence.
- **Authority without capacity drift** — decision authority remains formally assigned to agents whose actual capacity to evaluate the relevant signals has degraded through organizational distance, information asymmetry, or technical obsolescence.

CCL-F requires that drift across all three dimensions be tracked and registered. Static matching at program inception is not sufficient. The co-evolution condition must hold throughout.

**How it fails:** Engineers bear failure responsibility while executives capture financial benefits and schedule pressure determines authorization. The three-way misalignment is not accidental — it is often the equilibrium state of large organizations under competitive pressure.

**Why it matters:** Rule 5 violations are among the hardest to detect because the drift is gradual. No single decision produces the misalignment — it accumulates across a program lifecycle until the asymmetry is large enough to be catastrophic. R5.2 makes drift a trackable coordination property rather than an invisible background condition.

**What to do:** At program inception, register the explicit responsibility-authority-benefits mapping for each high-consequence failure mode. At each program milestone, audit the mapping for drift. Where drift is detected, treat it as an open coordination loop requiring evidence-based closure before irreversible execution proceeds.

**Cases:** Challenger — Thiokol engineers carried technical responsibility without launch veto authority. The static asymmetry was present from the outset and never corrected [5][6]. Boeing 737 MAX — the three-way drift pattern made visible: engineering responsibility, executive benefits from expedited certification, and a self-certification structure that removed independent authority to resolve the asymmetry [7]. Deepwater Horizon — BP’s well engineers bore operational responsibility while cost-cutting decisions that created the risk were made at institutional levels that captured the financial benefit of speed [10].

-----

### Rule 6: Decisions Produce Executable Next Steps

**What it requires:** Under ambiguity, decisions should produce reversible next steps rather than collapsing uncertainty into irreversible binary outcomes.

**How it fails:** Organizations under pressure reduce complex situations to forced choices: launch or don’t launch, proceed or halt. The binary framing eliminates the intermediate options — additional testing, delayed reassessment, temporary containment — that would preserve optionality while new information is gathered.

**Why it matters:** The absence of intermediate options is itself a coordination architecture failure. It removes the decision space that responsible action under uncertainty requires.

**What to do:** “Delay pending validation review” is always structurally available. Irreversible execution under unresolved ambiguity requires explicit justification, not just momentum.

**Cases:** The obvious next step before Challenger’s launch was to delay pending low-temperature seal validation. That option was structurally available and never formally generated [5][6]. After the Deepwater Horizon well showed anomalous pressure readings, the right intermediate step was another test. Instead, the ambiguous results were collapsed into a proceed decision under schedule pressure [10].

-----

### Rule 7: Recurring Coordination Failures Trigger Structural Review

**What it requires:** Recurrence is structural evidence. When the same failure mode appears repeatedly, the system must treat it as a signal that the coordination model requires reassessment — not as a series of isolated incidents to be managed individually.

**How it fails:** Each recurrence is closed by authority — someone senior acknowledges the anomaly and approves continuation. The pattern never accumulates into a recognized signal because each instance is treated as discrete.

**Why it matters:** Authority-based closure of recurring anomalies without evidence-based resolution is the organizational signature of a system adapting to incoherence rather than resolving it. See Rule 8.

**What to do:** When a recurrence group crosses the escalation threshold, structural review is mandatory and automatic — not a judgment call subject to schedule pressure or institutional momentum. Rule 7 fires the review. Rule 8 specifies what the review must produce.

**Cases:** Seven Challenger missions showed O-ring erosion. All seven were closed by authority. The escalation threshold was crossed after the third occurrence. No structural review was ever initiated [5][6]. Six Therac-25 patients received massive radiation overdoses before the incidents were connected. Each was treated as an isolated operator error rather than evidence of a systemic failure [11].

-----

### Rule 8: Systems Should Update Through Stress

**What it requires:** Stress signals must produce structural updates to the coordination model, not adaptive tolerance of unresolved incoherence. A system that survives without updating has failed this rule, even though it survived.

**How it fails:** The organization learns the wrong lesson. “We got away with it before” becomes implicit evidence that the current architecture is adequate. Risk tolerance expands without the underlying problem being resolved. Diane Vaughan called this normalization of deviance [9]. CCL-F frames it as an architectural failure: the coordination model was never updated to reflect what the evidence of recurrence demanded.

**Why it matters:** Rule 7 and Rule 8 are dependent. Rule 7 fires the structural review when recurrence crosses threshold. Rule 8 requires that the review produce a documented update to the coordination model — not a re-approval of existing practice. A system that detects the problem and fails to update has still failed.

**The distinction:**

- Adaptation: “We got away with it before — expand the definition of acceptable.”
- Update: “The system is signaling unresolved instability — change the coordination model.”

Only the second response satisfies Rule 8.

**Cases:** NASA flew six missions after O-ring erosion was first documented. Each flight that didn’t end in catastrophe made the next flight easier to authorize. The architecture never updated [5][6][9]. TEPCO’s own 2008 internal modeling showed that a tsunami exceeding the Fukushima seawall was possible. No pathway existed to convert that finding into a regulatory update. The organization adapted to the existence of unresolved risk rather than resolving it [12].

-----

### Rule 9: Stewardship Distribution Prevents Bottlenecks

**What it requires:** Coordination authority must be distributed close enough to operational conditions that local safety signals retain decision-relevant standing.

**How it fails:** Decision-making authority concentrates at the institutional center, away from operational reality. The people who know the most have the least power. The people with the most power are furthest from the signal.

**Why it matters:** A safety signal that reaches the organizational system but lacks standing to affect the decision has been suppressed by structure rather than by evidence. Rule 8 requires that the coordination model update when stress reveals incoherence. Rule 9 governs where the authority to act on that update must reside — close enough to operational conditions to be real rather than nominal.

**What to do:** Safety-bearing agents must have registered standing to halt or escalate — not merely to advise. The organizational architecture must be built so that proximity to the failure mode confers authority, not just obligation.

**Cases:** After Columbia’s launch, the Debris Assessment Team formally requested imagery to assess foam strike damage. The request was denied. The team had no registered standing — its requests were advisory, not binding [4]. Thiokol engineers knew the risk and said so. They had no veto. The organization had distributed advisory responsibility without distributing decision authority [5][6].

-----

## Layer 2 — Coordination Evaluation Semantics

Layer 1 describes how coordination loops should be managed. Layer 2 addresses the question Layer 1 leaves open: whether a loop actually closed, or was merely recorded as closed. It makes closure quality a formal, auditable property rather than an assumption — distinguishing genuine evidence-based resolution from authority-based override, administrative compression, and the other mechanisms by which organizations record resolution they have not achieved.

The deeper questions — whether closure is achievable at all across autonomous agents, which loops to prioritize under finite capacity, and where a system’s coordination state is heading — belong to Layer 3, Coordination Dynamics.

### Closure Quality

CCL-F distinguishes four types of closure, and treats them differently:

|Closure Type         |Definition                                                                                                                         |CCL-F Status                       |
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|
|Evidence closure     |New data or analysis resolves the constraint                                                                                       |Valid                              |
|Authority closure    |A senior agent overrides without new evidence                                                                                      |Flagged                            |
|Role-switch closure  |The same agent closes their own signal by changing roles                                                                           |Flagged                            |
|Authorization closure|A senior agent formally converts accumulated revision rigidity into a binding authorization record despite unresolved contradiction|Flagged — trajectory lock indicator|

Role-switch closure has a precise structural definition: an agent who holds an open signal in one organizational role reasserts a different role to close that same signal without producing new evidence. The roles need not be formally distinct — the reassertion may be informal, as when an agent is asked to reconsider a technical objection “from a management perspective.” What matters is that the same agent is simultaneously the registrant and the closer of the signal, with only a role boundary — not new evidence — separating the two acts. CCL-F flags this as role-switch closure — not blocked, but permanently recorded and requiring independent review. This is distinct from authority closure: authority closure involves a different agent overriding a signal; role-switch closure involves the same agent changing roles to override their own. The Challenger teleconference of January 27, 1986 is the canonical case [5][6].

### Evidence Novelty Requirement

Evidence-based closure requires that the closing evidence was not present when the signal was registered. Restating existing analysis in more confident language does not constitute new evidence.

### Ambiguity Debt

When uncertainty is compressed into nominal classifications rather than explicitly registered and tracked, it accumulates as ambiguity debt [2]. Unlike open loops — which are discrete and traceable — ambiguity debt is diffuse. It builds quietly across a program lifecycle until it combines with an irreversible execution decision and becomes catastrophic.

### Reversibility Logic

Closure quality requirements scale with the reversibility of the decision at stake. Irreversible decisions require evidence-based closure for all open constraint loops, or an explicit open-loop authorization with permanent audit logging.

### Escalation Conditions

The following conditions automatically escalate to structural review:

- Recurrence group threshold crossed (Rule 7)
- Operational state classified as off-envelope or containment
- Authority closure count exceeds threshold on an irreversible decision
- Role-switch closure detected on a safety-constraint signal
- Authorization closure detected in the presence of open constraint loops
- Suppressed signal detected before irreversible execution
- Framing signal achieves frame adoption while technical constraint signals remain open

### Loop Exit Taxonomy

A coordination loop ends in one of two ways: closure — genuine evidence-based resolution — or exit. Exit occurs when a loop is abandoned, suspended, transferred, or terminated without achieving genuine closure. CCL-F distinguishes fourteen exit types. Exit type determines what coordination obligations survive the exit, what audit trail is required, and whether the loop can or should be re-entered.

|Exit Type        |Mechanism                                                                                                                                              |Loop State After                                     |Primary CCL-F Layer|
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------|-------------------|
|**Terminal**     |Permanent disengagement; no re-entry pathway exists or is warranted                                                                                    |Closed by exit — permanently                         |Layer 2            |
|**Containment**  |System isolated pending evidence; interaction suspended, not terminated                                                                                |Quarantined — open, monitored                        |Layer 2            |
|**Recoverable**  |Suspension with explicitly defined re-entry conditions                                                                                                 |Paused — open, re-entry conditional                  |Layer 2            |
|**Superseded**   |Context that generated the loop no longer exists; loop rendered moot by external change                                                                |Void — closed by circumstance                        |Layer 2            |
|**Delegated**    |Closure authority formally transferred to another agent; loop remains open under new stewardship                                                       |Open — new steward registered                        |AP.1               |
|**Deferred**     |Loop acknowledged and explicitly parked pending conditions that do not yet exist                                                                       |Open — indefinite, documented                        |Layer 2            |
|**Forced**       |Agent removed from loop by organizational authority before closure; loop remains open                                                                  |Open — stewardship void risk                         |AP.1               |
|**Exhaustion**   |Agent’s coordination capacity depleted; loop remains open with no steward capacity to pursue it                                                        |Open — no active stewardship                         |Layer 3            |
|**Boundary**     |Autonomy boundary reached; agent’s closure authority ends at the boundary                                                                              |Open — non-closable by this agent                    |Layer 3            |
|**Timeout**      |Time sensitivity window closed before any exit decision was made; revision capacity expired                                                            |Terminal by default                                  |Layer 3            |
|**Ambiguity**    |Interpretive state unresolvable; agent exits under acknowledged uncertainty rather than false closure                                                  |Open — acknowledged, documented                      |Layer 2            |
|**Whistleblower**|Internal agent deliberately crosses autonomy boundary to force external loop registration after internal suppression                                   |Re-entered through external jurisdiction             |Layer 0 + Layer 2  |
|**Legal**        |External authority — regulatory body, court, executive order, or statutory trigger — supersedes agent closure authority                                |Suspended, transferred, or terminated by jurisdiction|Layer 0 + Layer 1  |
|**Key Person**   |Named steward becomes suddenly unavailable through death, incapacitation, resignation, or removal; loops become ownerless without registered succession|Stewardship void — open, unowned                     |AP.1               |

**Notes on specific exit types:**

*Whistleblower exit* is simultaneously a signal suppression event and a boundary exit. It is the observable indicator that a loop was suppressed to the point where internal closure became non-achievable and the registering agent exhausted internal escalation pathways. Roger Boisjoly’s post-Challenger testimony to the Rogers Commission is the canonical case [5][6].

*Legal exit* has four sub-types: regulatory intervention (a body orders halt or redesign), judicial order (a court compels or prohibits action), statutory trigger (law automatically terminates or transfers the loop when defined conditions are met), and investigative hold (external authority suspends a loop pending investigation). The Columbia investigation imposed an investigative hold on NASA’s return-to-flight decisions [4]. The FAA’s 737 MAX airworthiness directive was a regulatory intervention legal exit [7].

*Key person exit* reveals a single point of failure in stewardship structures and is the primary motivation for AP.1b Stewardship Succession. A key person exit in an AI deployment — the departure of the person who holds loop stewardship — can produce a stewardship void cascade across multiple loops simultaneously.

*Executive order exit* is a sub-type of legal exit that acts at Layer 0 rather than Layer 1 — it can restructure the coordination architecture itself, not just individual loops within it, potentially voiding existing stewardship assignments and boundary agreements that require re-registration from scratch.

**Exit obligations.** Every exit type generates audit trail obligations regardless of whether the loop is closed. An unregistered exit is structurally equivalent to a suppressed signal — the loop disappears from active monitoring while the hazard it named may persist. Terminal, legal, and key person exits require explicit notation of the open loop state at the time of exit. Delegated exits require successor registration before the exit is valid. Whistleblower exits require that the external escalation pathway and the suppression event that triggered it are permanently recorded.

-----

## Layer 3 — Coordination Dynamics

Layers 0 through 2 are largely static: they describe the architecture that must exist, the rules that must hold, and the criteria by which a loop is judged closed at a point in time. Layer 3 addresses the dynamic and directional character of coordination — the conditions under which closure is bounded, the loops worth prioritizing under finite capacity, the trajectory a system is on, and the progressive loss of revision capacity that ends in trajectory lock. Where Layer 2 asks whether a loop closed, Layer 3 asks whether closure is achievable at all, where the system is heading, and whether it can still change course.

### Distributed Closure Constraint

CCL-F does not assume that universal closure is achievable across autonomous agents. Closure authority is bounded by agent autonomy.

An agent operating within a coordination system may clarify intent, reduce ambiguity, transmit signal, withdraw participation, or locally resolve commitments. What an agent cannot do is finalize interpretive state within another autonomous system. The boundary of an agent’s closure authority is the boundary of their decision scope. Beyond that boundary, closure can be attempted but not enforced.

This constraint generates four distinct closure states that CCL-F tracks and treats differently:

**Local Closure** — A loop is resolved within the closing agent’s autonomous decision scope. The agent has reached interpretive stability and committed to a course of action. Local closure is valid and complete within its scope. It does not imply that other agents in the coordination system have reached equivalent resolution.

**Attempted Closure** — An agent has transmitted a closure signal across an autonomy boundary. The signal has been sent; reception and interpretive acceptance cannot be verified. Attempted closure is recorded as a coordination event but does not constitute loop resolution. It is the most common precursor to false closure.

**False Closure** — The system records a loop as closed while the underlying interpretive state remains unresolved across agent boundaries. False closure is structurally dangerous because it removes the loop from active monitoring while the hazard it named persists. Administrative compression is the most common mechanism of false closure in human organizations. In AI systems, optimization pressure toward task completion produces equivalent behavior.

**Globally Unresolved Distributed State** — No single agent can close the loop because resolution requires synchronized interpretive state across autonomous systems that cannot be forced into agreement. This condition may be intrinsic rather than accidental — a product of genuine autonomy rather than coordination failure. Recognizing a globally unresolved distributed state as such is itself a coordination achievement: it prevents false closure from being substituted for genuine resolution.

Many governance frameworks implicitly assume:

> Better Coordination ⟹ Convergence

CCL-F’s position is more precise:

> Coordination Capacity ≠ Guaranteed Interpretive Convergence

The distinction is not pessimistic — it is structural. A framework that assumes convergence is always achievable will systematically misclassify globally unresolved distributed states as coordination failures requiring more effort. CCL-F treats them as a distinct condition requiring a different response: explicit acknowledgment, documented open-loop authorization, and continuous monitoring rather than repeated closure attempts that produce only false closure.

**Cases:** The Challenger teleconference produced a globally unresolved distributed state. Thiokol engineers achieved local closure — they were interpretively stable on the risk and had formally registered it. NASA management achieved local closure — they had decided to proceed. The loop between them was never genuinely closed. Neither party could finalize interpretive state within the other’s autonomous decision scope. The system recorded a launch authorization. The underlying interpretive conflict remained unresolved [5][6]. The Katrina response produced the same condition at institutional scale. Each agency achieved local closure on its own response plan. No mechanism existed to synchronize their interpretive states into a unified operational picture — the globally unresolved distributed state was not the result of poor communication but of four genuinely autonomous systems that could not be forced into interpretive convergence under catastrophic conditions [8]. Multi-agent AI systems are the most important emerging domain for this constraint: an AI agent optimizing for task completion will, by default, treat attempted closure as equivalent to genuine closure, recording a loop as closed when a signal has been transmitted regardless of whether interpretive convergence has occurred on the other side of an autonomy boundary [16][17].

**Relationship to adjacent literature:** Pieces of this territory exist across distributed systems theory, cybernetics, epistemology, sociology, and multi-agent systems research. CCL-F’s contribution is the synthesis: autonomy-bounded closure brought directly into a governance coordination framework with explicit closure taxonomy semantics. The invariant — closure authority is bounded by agent autonomy — applies consistently across human organizations, institutional systems, and autonomous computational agents.

-----

### Loop Tractability Assessment

The Distributed Closure Constraint establishes that not all loops can be closed. The Loop Tractability Assessment addresses the operational consequence: given finite coordination capacity and structurally bounded closure authority, which loops should be prioritized for closure attempts?

CCL-F assesses loop tractability across two formally derived dimensions:

**Controllability** — whether the loop is within the closing agent’s autonomous decision scope. A loop is controllable if all agents whose interpretive state is required for genuine closure are within the coordinating agent’s authority boundary. Controllability is a structural property derivable from the coordination architecture — not a judgment. An agent either has the authority to produce genuine closure or they do not.

**Leverage** — the coordination consequence of leaving this loop open. Leverage is a function of the loop’s signal type (constraint loops carry higher leverage than uncertainty loops), its recurrence group membership (loops in active recurrence groups carry compounding leverage), its reversibility class (loops on irreversible decisions carry maximum leverage), and its position in the decision dependency graph (loops that block downstream decisions carry leverage proportional to the decisions they block).

These two dimensions distinguish CCL-F’s tractability assessment from superficially similar two-axis prioritization heuristics. The Eisenhower matrix uses urgency and importance — subjective judgments that different agents will assess differently for the same task. CCL-F’s axes are formally derivable from the coordination architecture and the commitment state machine. Two agents with access to the same architectural information should reach the same controllability and leverage assessments for the same loop.

**The four tractability quadrants:**

**High leverage, high controllability** — close these first. These are the loops that matter most and that the agent can genuinely resolve. The Challenger O-ring constraint was in this quadrant from NASA’s perspective — they had the authority to delay the launch and the loop was the most consequential open constraint in the system [5][6].

**High leverage, low controllability** — escalate and document. These loops matter enormously but cannot be closed unilaterally. The correct response is explicit acknowledgment as a globally unresolved distributed state, documented open-loop authorization if execution must proceed, and registered escalation to whatever coordination architecture exists above the autonomy boundary. Katrina’s inter-agency boundary incoherence was in this quadrant — the loops mattered enormously and no single agency controlled them [8].

**Low leverage, high controllability** — close if resources allow. These loops are within the agent’s authority but their resolution produces limited coordination benefit. Do not allow them to consume capacity that high-leverage loops require.

**Low leverage, low controllability** — accept and document. Do not attempt repeated closure that produces only false closure. These are intrinsic features of operating in a distributed autonomous environment, not failures of the coordination system.

**Time sensitivity — a third dimension recognized but not yet formally incorporated:**

A loop’s leverage is not static. It decays as execution proceeds and autonomy windows close. A loop that was high leverage and controllable at program inception may become uncontrollable by launch day — not because the architecture changed, but because the irreversible execution window has narrowed the available response space. CCL-F recognizes time sensitivity as a tractability modifier: the rate at which a loop’s controllability or leverage changes as execution proceeds. Formal treatment of time sensitivity as a decay function requires control theory and probability theory and is deferred to subsequent framework versions. The Challenger case remains its clearest illustration: the O-ring loop was high leverage and high controllability for months before launch day. By the night of January 27, the time window had compressed to hours. By launch morning, it had closed entirely [5][6].

**Scoring formalization deferred:** The controllability and leverage scores implied by this assessment require formal grounding in graph theory (decision dependency position), probability theory (leverage weighting), and control theory (time sensitivity decay functions). These formalizations are deferred pending completion of the mathematical foundation described in the Status section. The conceptual structure above is stable and is intended to guide the formalization rather than precede it.

-----

### Coordination Trajectory

CCL-F defines two distinct analytical dimensions for any coordination system at any point in time:

> State = current coordination condition

> Trajectory = predicted direction of state evolution under current constraints

> Current state constrains future trajectories.

**State** is a snapshot: the current closure topology, the current tractability assessment, the current revision capacity. It answers: where is this system now?

**Trajectory** is directional: the evolving revision capacity, the projected coordination stability, the expected closure evolution under current pressures. It answers: where is this system heading under current conditions?

The distinction matters because trajectory toward failure is detectable before failure occurs. The observable indicators of trajectory are derivable from existing framework variables:

- Unresolved loop accumulation rate
- Authority closure frequency relative to evidence closure frequency
- Recurrence normalization rate
- Revision latency — time between signal registration and closure attempt
- Boundary incoherence accumulation
- Time-window compression rate
- Revision rigidity index progression

When these indicators move in a consistent direction over time, they constitute a trajectory — a directional tendency that constrains future states without determining them.

**Three constraints govern trajectory claims in CCL-F:**

**Conditional, not deterministic.** CCL-F claims:

> “Under current unresolved pressures, the system trends toward increased trajectory lock risk.”

It does not claim:

> “This system will fail.”

Trajectory describes tendency. Current state constrains future trajectories — it does not eliminate them.

**Observable.** Trajectory indicators must derive from measurable framework variables. A trajectory claim unsupported by observable coordination state changes is not a CCL-F claim — it is speculation.

**Reversible.** A trajectory remains revisable unless irreversible execution thresholds have been crossed. The governance value of trajectory analysis is precisely that it identifies the window in which revision is still possible. A framework that produces fatalistic trajectory assessments has eliminated the intervention logic that makes it useful.

**Relationship to revision rigidity.** Revision rigidity is the primary trajectory indicator in CCL-F. As revision rigidity accumulates, the system’s trajectory shifts toward trajectory lock. The Revision Rigidity Index is therefore simultaneously a state measure (current revision capacity) and a trajectory measure (direction of revision capacity evolution). This dual function makes it the framework’s most operationally important metric.

**Trajectory formalization deferred.** A full formal treatment of coordination trajectory — including trajectory prediction functions, confidence intervals, and intervention point modeling — requires control theory, probability theory, and time-series analysis. These are deferred pending mathematical foundation completion. The conceptual structure above is stable.

-----

### Revision Rigidity and Trajectory Lock

CCL-F distinguishes signal visibility from interpretive update capacity.

> Signal visibility ≠ Interpretive update capacity

A system may observe a coordination signal, receive it, classify it correctly, and still be structurally incapable of revising its commitments in response. CCL-F formalizes this through two related concepts: revision rigidity and trajectory lock.

**Revision Rigidity** is the progressive loss of adaptive revision capacity under accumulated operational constraints. It is a process, not a state — measurable, observable, and reversible until a threshold is crossed. Revision rigidity accumulates through authority closure accumulation, recurrence normalization, time-window compression, benefit-responsibility drift, and the sources identified below.

**Trajectory Lock** is the terminal condition produced when revision rigidity reaches the irreversible execution threshold. A system in trajectory lock can receive signals, process evidence, and record closures — but can no longer revise its commitment trajectory before irreversible execution occurs.

> Revision Rigidity → Trajectory Lock

The framework’s central governance claim follows directly: by the time trajectory lock is reached, intervention is no longer available. The governance value of CCL-F lies in detecting revision rigidity accumulation before trajectory lock occurs.

Revision rigidity is distinct from the other closure failure modes CCL-F identifies:

- **False closure** records resolution without achieving it — the system claims the loop is closed when it isn’t
- **Globally unresolved distributed state** cannot be resolved because autonomous agents cannot be forced into interpretive convergence
- **Revision rigidity** is neither — the signal is present, reception has occurred, interpretive integration has begun, and revision capacity is degrading

The blocking mechanism is structural, not epistemic. The system does not lack the evidence. It lacks the capacity to act on it under current conditions.

**The four operations.** Genuine loop closure requires four distinct operations. Revision rigidity manifests as degradation in the third or fourth operation:

- **Evidence transmission** — the signal is sent and formally registered
- **Evidence reception** — the signal is received and enters the commitment process
- **Interpretive integration** — the received signal is processed against existing commitments
- **Commitment revision** — existing commitments are updated in response to the integrated evidence

Revision rigidity manifests at the third or fourth operation. The signal has been transmitted and received. Integration begins — and stops. Revision capacity is insufficient to produce an update.

**Sources of revision rigidity.** These mechanisms are not equivalent. They each reduce revision capacity through different organizational dynamics and require different interventions:

- **Institutional incentives** — the system is structured to reward non-revision; schedules, budgets, and performance metrics penalize delay
- **Sunk-cost dynamics** — prior investment makes revision feel like loss rather than correction
- **Time compression** — the execution window has narrowed to the point where revision is no longer operationally available; this is time sensitivity operationalized as a revision rigidity accelerant
- **Political pressure** — external authority is asserting a commitment the system cannot revise without organizational consequences
- **Identity protection** — revision would require acknowledging prior error
- **Normalization of deviance** — the system has adapted to treat the current trajectory as baseline; prior survival has been interpreted as validation [9]
- **Interpretive rigidity** — the classification framework itself has become resistant to update; new contradictory evidence is processed as noise rather than signal
- **Continuity Pressure Mechanism** — the organizational process collectively amplifying all the above: ambiguity normalization, responsibility diffusion, and rising revision thresholds under institutional pressure to preserve trajectory; produces the institutional state in which authorization closure becomes possible

**The Challenger case.** The Challenger launch authorization might have proceeded even if the CCL-F dashboard had been visible to every decision-maker in the teleconference. Not because the evidence was absent — it was present. Not because the signal failed — it was formally submitted. Not because the architecture was void. Revision rigidity had accumulated to trajectory lock, and two distinct mechanisms completed the failure.

The first was role-switch closure: the senior technical authority who had registered the engineering constraint against launch was asked to reconsider from a management perspective. The same agent, in a reasserted role, attempted to close the constraint he had opened — without new evidence [5][6].

The second was authorization closure: a different senior agent formally signed the launch recommendation, converting the organization’s accumulated revision rigidity into a binding coordination record. The institutional process had produced a state in which continuation felt more defensible than halt — and the authorization act made that state official and irreversible [5][6].

The Challenger revision rigidity trajectory: high revision capacity for months after the first O-ring anomaly; warning territory after the third; critical after the sixth; trajectory lock on the night of January 27; irreversible execution at 11:38 AM on January 28.

This reframes the Challenger failure at its deepest level — not as a failure of knowledge, signal transmission, or organizational architecture, but as a failure of revision capacity in a system that had accumulated rigidity to the point of trajectory lock, completed by two structural mechanisms that converted that rigidity into an irreversible authorization. That is not a moral claim. It is a structural one.

**Implications for the framework.** Revision rigidity and trajectory lock have three consequences for how CCL-F operates:

First, the coherence score must account for revision capacity, not just loop status. A system with all loops nominally open but high revision rigidity may have lower actual decision integrity than its coherence score suggests. Future versions of the coherence scoring model should incorporate revision rigidity indicators — recurrence normalization rate, authority closure accumulation, time sensitivity decay, and benefit-responsibility drift — as separate factors contributing to a Revision Rigidity Index.

Second, the dashboard’s function changes. Visibility is necessary but not sufficient. The dashboard must also surface revision rigidity accumulation so that trajectory lock risk is visible before the threshold is crossed, not after. The dashboard’s plain-language rendering is Revision Capacity Remaining — a continuous measure that communicates not the probability of disaster but the system’s diminishing ability to change its mind.

Third, the AI application becomes more urgent. An AI system optimizing for task completion is structurally predisposed to revision rigidity — it will treat existing commitments as stable baselines, interpret contradictory signals as noise, and resist revision unless explicitly required by the optimization objective. Without explicit revision pressure architected into the system, trajectory lock is the default terminal state [16][17].

**Relationship to adjacent literature.** Festinger’s cognitive dissonance theory addresses psychological resistance to belief revision. Argyris and Schön’s organizational learning theory distinguishes single-loop learning from double-loop learning — revision rigidity accumulating to trajectory lock is the failure of double-loop learning under operational pressure. Vaughan’s normalization of deviance [9] describes one specific revision rigidity accumulation mechanism as a cultural process. CCL-F’s contribution is to treat revision rigidity and trajectory lock as formal coordination properties rather than psychological, cultural, or cognitive phenomena — situating them within the framework’s existing state machine, closure taxonomy, and tractability assessment as trackable, monitorable conditions with defined precursors and defined interventions.

-----

### Loop Entanglement

Coordination loops are typically modeled as independent: each loop has its own signal, steward, closure condition, and lifecycle. Loop entanglement is the condition in which two or more loops are coupled such that the resolution state of each influences, constrains, or distorts the resolution of the others. Entangled loops cannot be evaluated independently without producing systematically distorted closure assessments.

Entanglement is not inherently pathological. Deliberately registered loop coupling is a valid governance structure — closing a safety verification loop as a prerequisite for opening an operational authorization loop is entanglement by design. What makes entanglement dangerous is when it is unregistered: the system treats coupled loops as independent, produces closure assessments that assume independence, and accumulates false closures and coordination debt without recognizing the structural source.

CCL-F requires that entangled loops be identified, their coupling conditions registered, and their resolution coordinated rather than treated independently.

**The Entanglement Spectrum**

Loop entanglement exists on a spectrum from mild coupling to full deadlock:

**Mutual Influence** — loops share signals, agents, or authority structures such that closing one changes the conditions under which the other operates. Coupling is weak and traceable. Registered mutual influence is a normal feature of well-designed coordination architectures.

**Mutual Constraint** — the closure conditions of each loop partially depend on the other’s resolution state. Neither loop can close cleanly without the other’s state affecting what counts as sufficient evidence. Treating the loops as independent produces distorted closure assessments — a loop may appear closed while a constraint from the coupled loop remains unresolved.

**Mutual Interference** — closure attempts in one loop actively destabilize the other. Attempting to close L₁ generates signals that reopen L₂, and vice versa. The system consumes coordination capacity without converging. This is the most operationally dangerous point on the spectrum because the system appears to be functioning — both loops are active and closure attempts are being made — while the underlying coupling prevents resolution.

**Deadlock** — full closure dependency. The closure condition of each loop requires the prior resolution of the other. Neither loop can achieve genuine evidence-based closure without the other closing first. Deadlock is the terminal entanglement condition.

> Closure(L₁) ⊇ f(state(L₂))
> Closure(L₂) ⊇ f(state(L₁))

**Failure Modes and the Resolution Pathway**

Unregistered loop entanglement produces three characteristic failure modes:

**False closure cascade** — one loop is administratively closed to permit the other to proceed. The second loop is then administratively closed on the assumption that the first is resolved. Neither achieved genuine resolution. Both are recorded as closed; both hazards persist.

**Indefinite deferral** — both loops remain open indefinitely because no agent has authority or capacity to break the entanglement. The system continues operating with permanently unresolved constraint loops, accumulating ambiguity debt in both simultaneously.

**Authority override cascade** — a senior agent closes both loops by authority to break the deadlock. Produces simultaneous authority closure flags across both loops and a sharp trajectory lock risk signal. The entanglement is dissolved by authority rather than resolved by evidence.

A fourth pathway is categorically distinct — it is the valid resolution mechanism, not a failure mode:

**Dependency dissolution exit** — one loop is deliberately superseded, delegated, or exited so that the other can close independently. A valid resolution when registered explicitly and when the exited loop’s consequences are acknowledged in the audit trail.

**Cases:** The Challenger launch decision produced a mutual interference entanglement between two loops: the O-ring thermal performance loop and the launch schedule loop. Closing the O-ring loop required halting launch. Closing the schedule loop required launching. Closure attempts in each loop destabilized the other. The system resolved through authority override cascade — management closed both loops by authority — producing the authorization closure event that converted accumulated revision rigidity into an irreversible launch record [5][6]. The Boeing 737 MAX self-certification structure produced a structural response to regulatory entanglement. The safety certification loop required operational data; the operational authorization loop required safety certification. The FAA’s ODA structure dissolved the dependency by merging both loops under Boeing’s authority — eliminating deadlock at the cost of eliminating the independence check that gave each loop its governance value [7]. Multi-party contract negotiation routinely produces mutual constraint entanglement: Party A will not commit without Party B’s commitment; Party B will not commit without Party A’s. Resolution mechanisms — escrow, conditional offers, simultaneous signing — are registered dependency dissolution strategies that break the entanglement by coordinating closure rather than treating the loops as independent.

**Relationship to other Layer 3 concepts.** Entangled loops accelerate revision rigidity accumulation — each failed closure attempt in a mutual interference or deadlock condition consumes coordination capacity and increases authority closure pressure. Entanglement also degrades loop tractability assessment: the controllability and leverage of each loop are distorted when evaluated independently, because the coupling means that closing a high-leverage loop may be impossible without simultaneously resolving a low-leverage one. Entangled loops produce the conditions under which the Continuity Pressure Mechanism most powerfully operates — the institutional pressure to preserve trajectory intensifies precisely when genuine resolution is structurally blocked.

**Registration requirement.** CCL-F treats unregistered loop entanglement as an Architecture Precondition failure. When two or more loops are identified as entangled, their coupling conditions must be explicitly registered as part of the coordination architecture — specifying the nature of the coupling (influence, constraint, interference, or deadlock), the agents responsible for coordinating resolution, the acceptable resolution pathways, and the escalation condition if the entanglement cannot be resolved before an irreversible execution window opens. Unregistered entanglement is structurally equivalent to an AP-A stewardship void: the loops appear to have independent stewards, but the coupling means that neither steward can close their loop without the other’s cooperation — and if that cooperation requirement is not registered, it does not exist in the coordination architecture.

-----

### Closure-Resistant Loop

An ordinary coordination loop fails to close because of architectural failure, process breakdown, or the bounded closure authority described in the Distributed Closure Constraint. A closure-resistant loop is a distinct pathology: the loop does not merely fail to close — it actively regenerates ambiguity by transforming disconfirming evidence into continuity-preserving interpretations.

In a normal loop, a closure signal produces closure:

> OPEN —[closure signal]→ CLOSED

In a closure-resistant loop, a reinterpretation operator R transforms the closure signal back into an open state:

> OPEN —[closure signal]→ R(OPEN)

R is not random. It activates when the cost of accepting closure exceeds the cost of reinterpretation:

> R activates when K_closure > K_reinterpretation

Where K_closure is the identity, social, or structural cost of accepting termination, and K_reinterpretation is the cognitive and coordination cost of preserving continuity through reinterpretation. When closure would require identity revision, status loss, institutional delegitimation, or acknowledgment of prior error, reinterpretation is often locally cheaper — and the loop self-preserves by metabolizing disconfirming evidence into continuation evidence.

**The reinterpretation operator.** R does not simply ignore evidence. It transforms it. Disconfirming signals are reinterpreted into forms compatible with continued trajectory:

- “No” becomes “uncertainty/testing”
- “Anomaly” becomes “acceptable operational variation”
- “Prior failure” becomes “evidence of robustness through survival”
- “Warning signal” becomes “insufficiently conclusive”
- “Boundary violation” becomes “signal of depth/significance”

Each transformation preserves the loop’s open state while consuming the closure signal that should have terminated it.

**Distinction from ordinary open loops.** An ordinary open loop has not yet received sufficient evidence for closure. A closure-resistant loop has received closure signals and transformed them. The distinction is operationally critical: ordinary open loops require more evidence; closure-resistant loops require different intervention — specifically, an intervention that changes the cost structure such that K_closure < K_reinterpretation.

**Distinction from the Continuity Pressure Mechanism.** The Continuity Pressure Mechanism is organizational: institutional pressure produces revision rigidity across the system. Closure-resistant loops are structural: a specific loop has developed an internal reinterpretation dynamic that prevents its own closure regardless of external coordination pressure. Both can co-occur — the Continuity Pressure Mechanism creates the organizational conditions under which individual loops become closure-resistant.

**The accountability intervention.** Accountability structures change the cost landscape by making reinterpretation more expensive than revision. Formal registration of a signal, explicit stewardship assignment, signed authorization records, and institutional documentation all increase K_reinterpretation by reducing plausible deniability, localizing responsibility, and coupling narrative coherence to operational outcomes. This explains why organizations systematically avoid explicit accountability locks — doing so would dissolve the cost advantage that makes reinterpretation the locally preferred strategy.

**Cases:** The Challenger teleconference produced multiple closure-resistant loops simultaneously. Engineering constraints against launch were registered and then transformed: uncertainty about O-ring failure became “insufficient proof of catastrophe”; prior erosion events became “evidence of survivability”; the burden of proof was inverted so that the default trajectory became continuation rather than halt. Each transformation consumed a closure signal and regenerated an open state [5][6]. Institutional denial following organizational crises routinely produces closure-resistant loops: evidence of systemic failure is transformed into localized anomaly, scapegoating, or isolated incident framing — preserving the narrative that the system fundamentally works while the structural failure persists unresolved.

**Generalization.** Closure-resistant loops appear across domains wherever the cost of accepting termination exceeds the cost of reinterpretation: conspiracy systems (disconfirming evidence becomes proof of conspiracy), sunk-cost escalation (prior investment becomes reason to continue), abusive relationship dynamics (boundary signals become tests of commitment), and organizational denial (system failure becomes individual error). CCL-F’s contribution is to treat closure resistance as a formal coordination property with an identifiable activation condition, a traceable reinterpretation mechanism, and a defined intervention logic — rather than as a psychological or moral failure.

-----

### Relationship Map — Layer 3 Concepts

The four core Layer 3 concepts are related but not synonymous. They describe different aspects of coordination system degradation, and conflating them produces misdiagnosis.

|Concept                   |What it describes                                                                                                                                                                            |Relation to the others                                                                                                                                          |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|**Revision rigidity**     |A progressive condition — the accumulating difficulty of revising a commitment once made, driven by organizational, structural, and cognitive sources                                        |The process; the other three are its products or expressions                                                                                                    |
|**Trajectory lock**       |The terminal state — revision capacity exhausted before genuine closure is achieved; irreversible execution proceeds with open loops                                                         |The end state of advanced revision rigidity accumulation                                                                                                        |
|**Closure-resistant loop**|A specific loop that has crossed the activation threshold where the cost of maintaining the interpretive frame exceeds the cost of genuine closure; the reinterpretation operator R is active|A local expression of revision rigidity at the individual loop level; trajectory lock is the system-level expression                                            |
|**Loop entanglement**     |A structural condition in which two or more loops are coupled such that each distorts the closure assessment of the others                                                                   |An architectural multiplier: entanglement amplifies revision rigidity and accelerates trajectory lock by making closure attempts in one loop destabilize another|

The degradation sequence in a failing system typically runs: entanglement goes unregistered → closure attempts in each loop generate authority closure rather than evidence closure → revision rigidity accumulates across the entangled cluster → individual loops become closure-resistant → system-level trajectory lock is reached. The sequence is not deterministic — any stage is reversible if detected and structurally addressed — but the direction is consistent with the historical record.

-----

## Layer 4 — Runtime Realization

Layer 4 is where the framework becomes a running system. The conceptual machinery of Layers 0 through 3 is realized as a commitment state machine, a coherence scoring model, execution gates, and an immutable audit trail. This layer is the basis for the eventual software implementation and the digital twin monitoring concept described in the Status section. The planned reference implementation is SignalGreen, an organizational coordination monitoring tool designed to instantiate the CCL-F runtime layer in a deployable product.

### Commitment State Machine

Every coordination signal moves through a defined lifecycle. The state machine enforces the rules structurally — certain transitions are blocked regardless of organizational pressure.

```
unregistered -> registered          (signal enters the system)
registered   -> classified          (Rule 2: required before review opens)
classified   -> under_review        (active analysis opened)
under_review -> closed_evidence     (new data resolves the constraint)
under_review -> closed_authority    (senior override, no new evidence)
under_review -> closed_role_switch  (same agent, different role)
under_review -> suppressed          (signal lost operational visibility)
under_review -> escalated           (recurrence threshold crossed)
under_review -> trajectory_lock     (revision capacity exhausted)

RECOVERY TRANSITIONS
escalated    -> under_review        (Rule 8 model update documented)
suppressed   -> under_review        (re-entry logged; suppression permanent)

REOPEN TRANSITIONS
closed_evidence    -> under_review  (evidence invalidated or recurrence link)
closed_authority   -> under_review  (new evidence or recurrence linkage)
closed_role_switch -> under_review  (mandatory independent review; L2 flag)

EXIT TRANSITIONS
any open state      -> exited(type) (fourteen types; see Loop Exit Taxonomy)
exited(recoverable) -> under_review (registered re-entry conditions met)
exited(delegated)   -> under_review (loop continues under new stewardship)
```

Four transitions are structurally blocked:

- A signal cannot be closed before it is classified
- A classified signal cannot be closed before review opens
- A suppressed signal cannot be silently closed
- A closed loop cannot be silently reopened — every reopen transition is permanently logged with rationale, the identity of the reopening agent, and the closure record it supersedes

Closed states are stable but not terminal. This is deliberate: false closure detection is central to the framework, and a state machine in which closure is irreversible cannot express the framework’s own core diagnostic — a loop recorded as closed while the underlying interpretive state remains unresolved. Reopening does not erase the original closure record; the audit trail retains both, and the closure-quality history of a loop (including how many times it has been reopened, and from which closure types) is itself a coordination signal feeding recurrence tracking and the coherence score.

The exit transitions integrate the Layer 2 Loop Exit Taxonomy directly into the runtime machine: every exit type is a recorded state carrying the audit obligations defined in Layer 2, and only the recoverable and delegated exits define re-entry paths. Terminal, timeout, and superseded exits are terminal states.

The `trajectory_lock` state is terminal and distinct from closure. A signal that reaches trajectory lock was received, classified, and reviewed — but revision capacity was exhausted before genuine closure could occur. It is recorded as a permanent marker that the loop remained open at the point irreversible execution proceeded. This is the state machine representation of the revision rigidity progression described in Layer 3.

### Coherence Score

The coherence score is a continuous 0.0-1.0 measure of decision integrity at a given decision node. It is not a pass/fail — it is a running assessment of how much epistemic confidence the current decision state actually warrants.

|Factor                  |Weight|
|------------------------|------|
|Open loops              |0.30  |
|Classification stability|0.25  |
|Closure quality         |0.20  |
|Recurrence pressure     |0.15  |
|Authority compression   |0.10  |

A score below the domain-configured threshold blocks irreversible execution pending acknowledgment.

The weights shown are provisional and illustrative — they encode the framework’s current qualitative judgment about relative factor importance, not an empirically validated model. Formal derivation of these weights is deferred pending the mathematical foundation described in the Status section. A future version will incorporate revision rigidity as a distinct sixth factor through a Revision Rigidity Index, capturing the trajectory dimension that the current five factors, all state measures, do not represent.

**Narrative Coherence and Operational Coherence.** The coherence score as defined above measures operational coordination integrity — how well the system’s decisions, signals, classifications, and closure events are aligned with evidence. A second coherence dimension is required to detect a distinct and dangerous failure mode: the decoupling of institutional narrative from operational reality.

CCL-F distinguishes:

> C_o = Operational Coherence — how well the system actually coordinates reality

> C_n = Narrative Coherence — how internally self-consistent the system’s story remains

> ΔC = C_n − C_o

A large positive ΔC is the measurable pathology: the story still works, but the system does not. Narrative coherence remains artificially stabilized through reinterpretation, authority closure, and continuity preservation while operational coherence quietly degrades. This is what Challenger exhibited for months — the narrative of NASA as a competent launch institution remained coherent right up to the moment operational reality made continuation impossible [5][6].

A large negative ΔC indicates a different condition: the system is functioning better than participants believe, which commonly appears during panic, institutional distrust, or crisis load.

Near-zero ΔC indicates healthy alignment between interpretation and operational reality.

The governance implication is precise: CCL-F’s job is not to destroy narrative coherence — healthy systems need mission, identity, confidence, and shared meaning. The intervention is to force narrative coherence to remain evidence-coupled rather than evidence-insulated. A healthy system maintains:

> dC_n/dt ≈ dC_o/dt

Narrative coherence tracks operational coherence. A pathological system allows C_n to remain stable while C_o decays — the story outlives the system’s ability to deliver on it.

The formal coherence scoring model will eventually incorporate ΔC as a divergence measure. For now, the operational diagnostic is: when narrative coherence is preserved by reinterpretation faster than operational coherence can be repaired, the system is drifting toward closure-resistant pathology.

### Execution Gates

|Execution Class|Requirements                                                                                                       |
|---------------|-------------------------------------------------------------------------------------------------------------------|
|Irreversible   |No open constraint loops; classification stabilized; recurrence groups reviewed; minimum evidence closure ratio met|
|Elevated       |Classification acknowledged; open loops documented                                                                 |
|Routine        |Signal registration complete                                                                                       |

Gates can be overridden. Every override is permanently logged with the agent’s identity, rationale, and timestamp. The system does not prevent decisions. It makes the epistemic quality of decisions visible, auditable, and permanent.

### Audit Trail

Every state transition is append-only and immutable. The audit trail supports full post-mortem replay from any point in the program history, prospective intervention point identification, and open-loop authorization accountability. The record cannot be revised after the fact — only extended.

-----

## Failure Taxonomy Across Historical and Emerging Cases

Each case is mapped to the CCL-F layers and rules that its primary failure most clearly instantiates. Some cases appear more than once because they exhibit distinct failure patterns across independent rule dimensions — each row represents a different analytic lens on the same event, not a duplicate entry.

|Case                                           |Primary Layer    |Primary Failure                                                      |Key Mechanism                                                                                                                                                                                                                                                                               |
|-----------------------------------------------|-----------------|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Challenger (1986) [5][6]                       |Layer 0 + Layer 1|Rule 2 + Role-switch closure + Authorization closure + Framing signal|Stewardship void under off-envelope conditions; misclassification; framing signal inverted burden of proof; role-switch closure attempted to close the engineering constraint without new evidence; authorization closure converted accumulated revision rigidity into binding launch record|
|Challenger (1986) — recurrence dimension [5][6]|Layer 1          |Rule 7 + Rule 8 + Rule 9                                             |Seven O-ring anomalies never triggered structural review (Rule 7); the coordination model never updated (Rule 8); stewardship for off-envelope authorization was never distributed to engineering (Rule 9)                                                                                  |
|Columbia (2003) [4]                            |Layer 0 + Layer 1|Rule 1 + Rule 9                                                      |Signal suppression; the Debris Assessment Team had no organizational standing — its requests were advisory, not binding                                                                                                                                                                     |
|Boeing 737 MAX (2018) [7]                      |Layer 0 + Layer 1|Rule 2 + Rule 3                                                      |Deliberate misclassification; boundary incoherence encoded into the regulatory architecture                                                                                                                                                                                                 |
|Deepwater Horizon (2010) [10]                  |Layer 1          |Rule 6 + Rule 7 + Rule 5.2                                           |Ambiguity collapsed to binary; recurrence normalization without coordination model update; responsibility-authority-benefits drift — well engineers bore operational risk while institutional levels captured the financial benefit of speed                                                |
|Fukushima (2011) [12]                          |Layer 0 + Layer 1|Rule 8 + AP-B                                                        |Channel collapse; no pathway to convert internal risk findings into a regulatory coordination model update                                                                                                                                                                                  |
|Therac-25 (1985) [11]                          |Layer 1          |Rule 7 + Rule 1                                                      |Six overdoses treated as isolated incidents; recurrence never linked; authority closure without evidence                                                                                                                                                                                    |
|Hurricane Katrina (2005) [8]                   |Layer 0          |The Architecture Precondition — all subtypes                         |Simultaneous stewardship void, channel collapse, and boundary incoherence across four agencies; the Hurricane Pam exercise identified these voids prospectively and they were never closed                                                                                                  |
|AI deployment (emerging) [16][17]              |Layer 0          |The Architecture Precondition — all subtypes                         |“The AI is responsible” is a stewardship void; no verified pathway from AI anomaly signals to human review is a channel collapse; multi-organizational AI deployments under assumed agreements are boundary-incoherent by definition                                                        |

-----

## Validation and the Selection Problem

Every case in the taxonomy above is a retrospective canonical disaster, and the framework should name the methodological consequence before a reviewer does. Mapping CCL-F categories onto known failures demonstrates expressive adequacy — the framework can describe what happened. It does not, by itself, demonstrate diagnostic power. Any sufficiently rich vocabulary fits known disasters after the fact; the post-hoc application of structural categories to selected catastrophes is exactly the move that distinguishes weak applications of normalization-of-deviance theory from Vaughan’s original ethnographic work [6][9].

Diagnostic power requires negative cases, of two kinds:

**Survivor cases.** Systems exhibiting elevated CCL-F indicators — authority closure accumulation, recurrence normalization, rising ΔC — that did not fail, or that operated for extended periods without catastrophe. If the indicators are equally elevated in failure and non-failure populations, they measure organizational life under pressure, not failure trajectory. The high reliability organization literature [14] identifies candidate survivor populations — carrier flight operations, nuclear power plant operations, air traffic control — whose indicator profiles can be compared against the failure corpus.

**Recovery cases.** Systems in which revision occurred late but before irreversible execution. The most valuable comparison set is within-organization: NASA scrubbed shuttle launches on engineering constraint signals throughout the same program that produced Challenger. The scrub decisions and the Challenger authorization moved through the same coordination architecture with different outcomes. What distinguished them — closure quality, revision capacity remaining, time-window position — is precisely what the framework claims to measure, and the comparison controls for organization, program, and era in a way that cross-organization comparisons cannot.

The design consequence is a sampling rule: the planned empirical corpus must be sampled on indicators, not on outcomes. Select organizational periods by indicator level, then observe the outcome distribution — rather than selecting disasters and confirming that indicators were present. The second design cannot fail; the first can, which is what makes it evidence.

A further measurement constraint applies to historical validation. Several CCL-F indicators — revision latency, recurrence normalization rate, authority-to-evidence closure ratio — presuppose the registration infrastructure CCL-F itself would install. Pre-adoption organizations do not log closure quality. Historical validation therefore requires proxy construction: closure events reconstructed from meeting minutes, waiver records, anomaly dispositions, and investigation testimony, with the proxy-to-indicator mapping documented and its limitations stated. The framework’s claims are testable on historical data only to the degree that these proxies are defensible, and proxy construction is itself a deliverable of the validation program, not an afterthought.

-----

## Relationship to STAMP/STPA

CCL-F is complementary to Leveson’s STAMP framework, not competitive with it [1][13]. The distinction is precise enough to state in one sentence:

> STAMP identifies what safety constraints must be enforced. CCL-F tracks whether the organizational commitment process actually enforces them — and distinguishes between constraints that were genuinely resolved and constraints that were merely administratively compressed.

STAMP and its associated methods operate at two points in a program’s lifecycle:

|Framework|When                      |What It Does                                                                  |
|---------|--------------------------|------------------------------------------------------------------------------|
|STPA [13]|Before the system is built|Identifies unsafe control actions at design time                              |
|STAMP [1]|After an accident         |Models how control structure failure caused the disaster                      |
|CAST [1] |After an accident         |Investigates causation using the STAMP model                                  |
|CCL-F    |Continuously              |Tracks commitment integrity from signal registration through execution closure|

The timing difference is the key differentiator. STAMP and CAST are retrospective. CCL-F is designed to operate at runtime — to fire before the disaster, not to explain it afterward.

**Adjacent literature:** CCL-F also engages several related bodies of work. Malone and Crowston’s coordination theory [2] defines coordination as managing dependencies; CCL-F extends this with commitment state tracking and closure quality evaluation. Vaughan’s normalization of deviance research [9] describes the cultural process by which anomalous signals are progressively reclassified as acceptable; CCL-F provides the structural mechanism that makes this process possible. Weick and Sutcliffe’s high reliability organization research [14] describes organizations that resist this drift; CCL-F formalizes what they do implicitly. Beer’s Viable System Model [15] provides a cybernetic management framework; CCL-F is more specific, focusing on commitment dynamics rather than organizational viability in the general sense.

-----

## Key Definitions

**Coordination Signal (CS):** A safety-relevant input that enters the organizational commitment process and requires evidence-based closure before irreversible execution.

**Steward:** The named agent or organizational unit that has explicitly accepted closure responsibility for a coordination loop or high-consequence failure mode. CCL-F uses *steward* rather than *owner* to emphasize that closure responsibility is an accepted obligation rather than a property right — a steward holds responsibility on behalf of the system, not possession of it. In STAMP, ITIL, ISO risk frameworks, and most aerospace governance documentation, the equivalent term is *owner*. The concepts are functionally equivalent; the distinction is intentional. Stewardship requires both active assignment (AP.1a) and registered succession (AP.1b).

**Stewardship Succession:** The registered designation of a named successor for every high-consequence failure mode steward. Required by AP.1b. A steward without a registered successor is a single point of failure in the coordination architecture. Stewardship succession converts a single-agent stewardship assignment into a resilient stewardship structure that survives planned and unplanned steward unavailability.

**Commitment State:** The current lifecycle position of a coordination signal within the CCL-F state machine.

**Operational State:** The formally classified condition of a system at a given decision point. CCL-F defines five operational states:

- **Nominal** — system operating within validated parameters; all relevant variables within tested ranges; no unresolved anomalies. Standard coordination rules apply.
- **Elevated Uncertainty** — system operating within tested parameters but with one or more registered, unresolved interpretive uncertainties. Action is permitted; open uncertainty loops must be documented and tracked.
- **Off-Envelope** — one or more operating parameters outside validated test data. The system is functioning in conditions for which no validated performance data exists. Evidence-based classification required before irreversible execution; authority closure flagged.
- **Experimental** — system operating under conditions deliberately designated as unvalidated and under active investigation. Distinct from off-envelope in that the unvalidated condition is acknowledged and formally managed rather than misclassified.
- **Containment** — active anomaly management in progress. A failure mode has been identified and is being actively managed. Irreversible execution requires extraordinary justification and independent steward review.

Classification into any state other than nominal does not block execution — it determines what coordination requirements apply. Misclassifying an off-envelope or containment condition as nominal does not relax those requirements; it conceals them.

**Commitment Layer:** The organizational process by which known safety signals are transformed — or fail to be transformed — into executable decisions. This is the layer STAMP does not model [1] and CCL-F specifically addresses. A signal can be technically present and correctly identified at the control structure layer while still failing at the commitment layer — which is precisely the class of failure CCL-F is designed to detect.

**Closure Quality:** The epistemic basis on which a coordination loop is considered resolved. Evidence-based, authority-based, and role-switch closures are categorically distinct and are tracked separately.

**Framing Signal:** A coordination signal whose content is an interpretive frame rather than a technical constraint. Its function is to shift how other signals are understood — to stabilize or destabilize the organizational classification of an operational state. Its closure mechanism is frame adoption rather than evidence resolution. When a framing signal achieves frame adoption while technical constraint signals remain open, CCL-F classifies this as an authority closure of the framing signal combined with a suppression event on the signals it displaced. Framing signals are distinct from dissent signals: dissent challenges a decision directly; framing recontextualizes the conditions under which decisions are made. CCL-F handles framing signals inside the commitment process. The extra-systemic dynamics governing how framing signals acquire legitimacy before entering that process are addressed in the adjacent Interpretive Power framework.

**Role-Switch Closure:** The closure failure mode in which the agent who registered a safety constraint attempts to close it by reasserting a different organizational role rather than producing new evidence. The registrant and the closer are the same person, separated only by a role boundary — not by new evidence. CCL-F classifies this as flagged, permanently logged, and requiring independent review. It is distinct from authority closure: authority closure involves a different agent overriding a signal; role-switch closure involves the same agent changing roles to override their own. The Challenger teleconference of January 27, 1986 is the canonical case [5][6].

**Authorization Closure:** The structural act by which a senior agent formally converts accumulated institutional revision rigidity into a binding coordination record by authorizing continuation despite unresolved operational contradiction. Authorization closure is not a single decision made under pressure — it is the point at which the Continuity Pressure Mechanism produces an irreversible organizational commitment. The agent who performs authorization closure may be acting rationally within the institutional logic the system has produced; the failure is structural, not personal. Authorization closure is flagged, permanently logged, and treated as a trajectory lock indicator when it occurs in the presence of open constraint loops.

**Continuity Pressure Mechanism:** The organizational process by which revision rigidity accumulates through ambiguity normalization, responsibility diffusion, and rising revision thresholds under institutional pressure to preserve trajectory. The Continuity Pressure Mechanism is the organizational-level dynamic that makes authorization closure possible — it produces the institutional state in which continuation feels more defensible than revision. Observable indicators: rising authority closure frequency, recurrence normalization without structural review, progressive decoupling of responsibility and authority, and narrowing of the time sensitivity window without corresponding escalation. Distinguished from Provisional Continuation by the absence of explicitly registered open uncertainty: the Continuity Pressure Mechanism closes interpretive questions by institutional pressure; Provisional Continuation holds them explicitly open.

**Provisional Continuation:** The adaptive coordination mechanism by which a system maintains trajectory under acknowledged interpretive instability, explicitly holding open the question of whether instability is terminal or transitional, with defined re-evaluation conditions. Provisional Continuation is the resilient counterpart to the Continuity Pressure Mechanism: both involve continuation under uncertainty, but Provisional Continuation preserves revision capacity while the Continuity Pressure Mechanism degrades it. Observable indicator: the instability signal remains registered as open in the commitment process, with explicit re-evaluation conditions defined. Examples include fault-tolerant engineering systems, long-term research programs, diplomatic negotiations, and organizational change processes where premature termination would be the worse error.

**Ambiguity Debt:** The accumulation of unresolved interpretive uncertainty across a program lifecycle [2]. Ambiguity debt builds when uncertainty is compressed into nominal classifications rather than explicitly registered and tracked. Unlike open loops — which are discrete and traceable — ambiguity debt is diffuse and systemic, which makes it harder to detect without continuous monitoring.

**Architecture Void:** A condition in which coordination loops are structurally non-closable due to absent, unverified, or incoherent coordination architecture.

**Coordination Non-Instantiation:** The condition in which no operationally valid coordination loop exists to fail — distinct from coordination failure, in which a loop exists but fails to close.

**Recurrence Group:** A set of linked coordination signals sharing a common failure mode, tracked across the program lifecycle for escalation threshold purposes.

**Coherence Score:** A continuous measure of decision integrity at a given decision node, incorporating open loop count, classification stability, closure quality, recurrence pressure, and authority compression.

**Responsibility-Authority-Benefits Drift:** The gradual decoupling of an agent’s failure responsibility, decision authority, and institutional benefits over a program lifecycle. Drift across any of the three dimensions constitutes a coordination asymmetry under Rule 5.2 and must be tracked and registered. Static matching at program inception does not satisfy the co-evolution condition.

**Open-Loop Irreversible Execution:** Proceeding with an irreversible decision while one or more coordination loops remain open. Permitted with explicit authorization — permanently logged.

**Loop Exit:** The termination, suspension, transfer, or abandonment of a coordination loop without achieving genuine evidence-based closure. CCL-F defines fourteen exit types: terminal, containment, recoverable, superseded, delegated, deferred, forced, exhaustion, boundary, timeout, ambiguity, whistleblower, legal, and key person. Every exit type generates audit trail obligations; an unregistered exit is structurally equivalent to a suppressed signal. See Layer 2 — Loop Exit Taxonomy for full definitions.

**Loop Entanglement:** The condition in which two or more coordination loops are coupled such that the resolution state of each influences, constrains, or distorts the resolution of the others. Entangled loops cannot be evaluated independently without producing systematically distorted closure assessments. CCL-F distinguishes four entanglement levels: mutual influence (weak, traceable coupling), mutual constraint (partial closure dependency), mutual interference (closure attempts destabilize each other), and deadlock (full closure dependency — neither loop can close without the other closing first). Unregistered entanglement is treated as an Architecture Precondition failure equivalent to an AP-A stewardship void. See Layer 3 — Loop Entanglement for full treatment.

**Local Closure:** A coordination loop resolved within the closing agent’s autonomous decision scope. Valid and complete within its scope. Does not imply that other agents in the coordination system have reached equivalent resolution.

**Attempted Closure:** A closure signal transmitted across an autonomy boundary. Reception and interpretive acceptance cannot be verified. Recorded as a coordination event but does not constitute loop resolution. The most common precursor to false closure.

**False Closure:** A loop recorded as closed while the underlying interpretive state remains unresolved across agent boundaries. Structurally dangerous because it removes the loop from active monitoring while the hazard it named persists.

**Globally Unresolved Distributed State:** A condition in which no single agent can close a loop because resolution requires synchronized interpretive state across autonomous systems that cannot be forced into agreement. May be intrinsic rather than accidental. Recognizing this condition as such — rather than substituting false closure — is itself a coordination achievement.

**Controllability:** A formal property of a coordination loop expressing whether the loop is within the closing agent’s autonomous decision scope. A loop is controllable if all agents whose interpretive state is required for genuine closure are within the coordinating agent’s authority boundary. Derivable from the coordination architecture.

**Leverage:** The coordination consequence of leaving a loop open. A function of the loop’s signal type, recurrence group membership, reversibility class, and position in the decision dependency graph. Formally derivable from the commitment state machine.

**Time Sensitivity:** A recognized tractability modifier expressing the rate at which a loop’s controllability or leverage changes as execution proceeds. Formally deferred pending control theory and probability theory foundations.

**Revision Rigidity:** The progressive loss of adaptive revision capacity under accumulated operational constraints. A process, not a binary state — measurable, observable, and reversible until the trajectory lock threshold is crossed. Accumulates through authority closure accumulation, recurrence normalization, time-window compression, benefit-responsibility drift, institutional incentives, sunk-cost dynamics, political pressure, identity protection, and interpretive rigidity.

**Trajectory Lock:** The terminal condition produced when revision rigidity reaches the irreversible execution threshold. A system in trajectory lock can receive signals, process evidence, and record closures — but can no longer revise its commitment trajectory before irreversible execution occurs. Trajectory lock is what CCL-F is designed to detect before it is reached, not explain after it has produced catastrophe.

**Coordination Trajectory:** The predicted direction of coordination state evolution under current constraints. Trajectory is directional tendency — not destiny. Current state constrains future trajectories without determining them. Observable through unresolved loop accumulation rate, authority closure frequency, recurrence normalization rate, revision latency, and revision rigidity index progression.

**Revision Capacity Remaining:** The dashboard’s plain-language rendering of the Revision Rigidity Index. Communicates the system’s diminishing ability to change its mind — not the probability of disaster. Operational zones: high (78-100%, system adaptable), warning (42-77%, revision capacity degrading), critical (9-41%, effectively locked), irreversible (0-8%, trajectory lock threshold).

**Corrigibility:** A coordination system’s preserved capacity to recognize when its assumptions, classifications, or commitments no longer match operational conditions and to revise its behavior accordingly. Corrigibility is not the absence of error — it is the preserved ability to revise under error. A highly corrigible system can still be disciplined, coherent, resilient, and mission-oriented; the key property is that revision remains possible when evidence thresholds are crossed. Corrigibility degrades as revision rigidity accumulates and is lost at trajectory lock. CCL-F’s intervention logic is directed at preserving corrigibility — detecting the conditions that degrade it before irreversible execution removes it entirely. Coherence is healthy only when it remains corrigible. *Operationalization: corrigibility is a formal metrics target in the validation program, expressible as a function of the authority-to-evidence closure ratio, revision latency, and recurrence normalization rate over time; precise measurement specification is future work.*

**Narrative Coherence (C_n):** The internal self-consistency of a system’s organizing story — its mission narrative, institutional identity, and interpretive framework. Narrative coherence can remain artificially high through reinterpretation and authority closure while operational coherence degrades. The gap ΔC = C_n − C_o is a diagnostic measure of closure-resistant drift.

**Operational Coherence (C_o):** The alignment between a system’s decisions, classifications, closure events, and operational reality. Measured by the existing coherence score factors. Degrades when ambiguity debt accumulates, authority closures dominate, recurrence is normalized, and revision capacity is consumed.

**Closure-Resistant Loop:** A coordination loop that actively regenerates ambiguity by transforming disconfirming evidence into continuity-preserving interpretations through a reinterpretation operator R. Activates when closure cost exceeds reinterpretation cost (K_closure > K_reinterpretation). Distinct from an ordinary open loop, which has not received sufficient closure signals; a closure-resistant loop has received closure signals and metabolized them. See Layer 3 — Closure-Resistant Loop.

-----

## The Central Claims

CCL-F makes eight central claims. They are not epistemically uniform, and the framework gains nothing by pretending otherwise. Some are framework commitments — architectural and definitional positions that structure what CCL-F measures. These are evaluated by coherence, diagnostic utility, and the quality of the distinctions they enable, not by falsification; no observation could disconfirm a definition. Others carry empirical content: they generate predictions that historical and operational data can confirm or disconfirm. Each claim is labeled, and each empirical claim states the observation that would count against it. The empirical claims are testable subject to the proxy-construction constraint described in Validation and the Selection Problem.

**Claim 1 — Classification integrity is a prerequisite gate** *(Rule 2).* No execution-class decision is valid without explicit operational state classification, and unvalidated conditions cannot be classified as nominal. Existing practice contains partial versions of this discipline — NASA launch commit criteria, operating-envelope limits in airworthiness certification, risk classification under ISO 31000 — but these govern whether parameters are within limits, not whether the classification act itself was evidence-based, and none makes misclassification a tracked, flagged, audit-logged event in the commitment process [1][13]. *Status: framework commitment, with a checkable comparative component — the claim of distinctiveness fails if a major safety framework is identified that formally gates execution on evidence-based state classification with equivalent audit consequences.*

**Claim 2 — Closure quality is trackable and consequential** *(Layer 2).* The difference between evidence-based closure and authority-based closure is measurable and auditable. Current systems treat all closures as equivalent. CCL-F does not. *Status: empirical. Prediction: failure modes whose loops show a rising authority-to-evidence closure ratio will exhibit higher recurrence and escalation rates than matched failure modes where the ratio is stable. Disconfirmation: no outcome difference by closure type.*

**Claim 3 — Recurrence is structural evidence requiring a coordination model update** *(Rules 7 and 8).* Escalation at recurrence threshold is automatic — not a judgment call subject to schedule pressure or institutional momentum [9]. The output of structural review must be a documented update to the coordination model, not a re-approval of existing practice. Rule 7 detects. Rule 8 specifies what detection must produce. *Status: mixed. The escalation requirement is a framework commitment. The empirical kernel: catastrophic failures are disproportionately preceded by recurrence groups repeatedly closed by authority without structural review, relative to matched non-failure periods in the same systems. Disconfirmation: unreviewed recurrence groups are equally common before failures and non-failures.*

**Claim 4 — Coordination evaluability has architectural preconditions** *(The Architecture Precondition).* Before asking whether coordination loops are closed, verify that the architecture required to close them exists. An architecture void renders all other coordination assessment meaningless. *Status: framework commitment. Not falsifiable as stated, and not presented as such — its defense is diagnostic utility: the precondition distinguishes failure classes (Katrina, AI deployment) that frameworks assuming an intact architecture cannot separate.*

**Claim 5 — Closure authority is bounded by agent autonomy** *(Distributed Closure Constraint).* Not all loops are closable regardless of coordination effort or architectural completeness. The distinction between local closure, attempted closure, false closure, and globally unresolved distributed states is a formal property of the coordination system — not a failure mode to be corrected. *Status: framework commitment with an empirical corollary. Prediction: interventions that treat globally unresolved distributed states as solvable coordination failures — repeated closure attempts across autonomy boundaries — produce higher false-closure rates than interventions that register the state explicitly and monitor it. Disconfirmation: repeated closure attempts resolve such states at rates comparable to explicit registration.*

**Claim 6 — Loop tractability is formally assessable** *(Loop Tractability Assessment).* Given finite coordination capacity, controllability and leverage are derivable properties of the coordination architecture and commitment state machine — not subjective judgments. *Status: empirical, with a direct inter-rater test. Prediction: independent assessors given the same coordination architecture documentation reach concordant controllability and leverage assessments at rates significantly exceeding the concordance achieved with urgency/importance heuristics on the same loops. Disconfirmation: inter-rater reliability no better than the Eisenhower matrix.*

**Claim 7 — Signal visibility does not guarantee interpretive update capacity** *(Revision Rigidity and Trajectory Lock).* A system may observe, receive, and correctly classify a coordination signal while revision capacity is degrading toward trajectory lock. Revision rigidity is a progressive, measurable, and reversible coordination condition with identifiable precursors — not a moral failure or epistemic deficiency. *Status: empirical. Prediction: revision rigidity indicators — authority closure accumulation, recurrence normalization rate, revision latency — rise in the period preceding failures of commitment revision, and decline following accountability interventions that change the closure cost structure. Disconfirmation: indicator levels uncorrelated with subsequent revision outcomes.*

**Claim 8 — Coordination trajectory is a measurable property of system state** *(Coordination Trajectory).* Current coordination state constrains future trajectories. Trajectory toward revision rigidity and trajectory lock is detectable before irreversible thresholds are crossed, through observable indicators derivable from existing framework variables. CCL-F does not predict failure — it identifies the directional tendency of system state under current conditions, preserving the intervention logic that makes governance frameworks useful. *Status: empirical, and the framework’s central testable claim. Prediction: trajectory indicators trend consistently in the periods preceding catastrophic failures and do not trend equivalently in indicator-matched non-failure periods. This is the prediction the negative-case corpus described in Validation and the Selection Problem is designed to test, and the claim on which the framework’s prospective-detection value stands or falls.*

-----

## AI Applications

CCL-F was developed to explain organizational failures in human systems. Its application to AI follows directly — and may prove more consequential than the original framing.

### The Core Problem

An AI system optimizing for task completion will, by default, treat authority-based and evidence-based closures as equivalent, accept role-switch closures without flagging them, normalize recurrence rather than escalating it, and classify off-envelope conditions as nominal when the training distribution suggests acceptability. These are not failures of alignment in the reward-specification sense [16]. They are coordination architecture failures — precisely the class CCL-F was designed to detect.

The Challenger parallel holds. The disaster happened because a valid safety signal entered an organizational commitment process and failed to survive it. The analogous AI failure is already occurring at smaller scales: AI systems receive safety-relevant signals, process them, and fail to route them to closure because the organizational architecture governing their operation was never formally registered. Nobody owns the loop. The channel is unverified. The boundary agreements between the AI and its human oversight layer are assumed rather than explicit.

### Three Applications

**AI as Coordination Signal Classifier.** CCL-F’s ingestion layer requires a machine learning component to identify coordination signals in organizational data streams — detecting when a communication, document, or decision event constitutes a safety-relevant signal requiring state tracking. An AI classifier trained on CCL-F’s six signal types would enable automated coordination integrity monitoring at organizational scale. This is the most immediate product application.

**CCL-F as Behavioral Specification for AI Agents (future work).** A longer-term application is CCL-F as a behavioral safety specification for AI agents operating in coordination-critical environments — requiring that an agent never classify off-envelope conditions as nominal without validating evidence, flag authority-based and role-switch closure attempts, escalate recurrence groups automatically at threshold, and refuse to authorize irreversible execution with open constraint loops unless override is explicitly acknowledged and logged. The analogy to how DO-178C [18] specifies software behavior for safety-critical aviation systems is instructive but remains to be worked out formally; this is identified as a future work direction rather than a current equivalence claim.

**The Architecture Precondition Applied to AI Deployment.** Before deploying an AI agent in any high-consequence environment, the Architecture Precondition requires that the coordination architecture governing that deployment be complete, verified, and boundary-coherent. “The AI is responsible” is not a stewardship assignment — it is a stewardship void. The Architecture Precondition applied to AI governance produces a concrete, auditable deployment checklist: not “is the AI aligned,” but “is the organizational architecture surrounding the AI capable of detecting and routing its safety-relevant signals to evidence-based closure before irreversible execution?”

### The Gap

Current AI alignment frameworks address reward specification, value learning, corrigibility, and interpretability [16][17]. None addresses the organizational commitment layer. They assume that if the AI produces the right signals, the surrounding architecture will route them appropriately. CCL-F makes no such assumption.

The question CCL-F adds to the AI safety agenda is the one none of these frameworks currently answer:

> Even if the AI produces the right signals, is the organizational architecture surrounding it capable of converting those signals into evidence-based closure before irreversible execution?

### Future Research Directions

- Formal specification of coordination-coherent AI agent behavior using TLA+
- Empirical study of AI coordination failures in healthcare, financial systems, and autonomous vehicles
- The Architecture Precondition compliance frameworks for AI governance and deployment
- AI-assisted coordination monitoring at organizational scale
- Extending CCL-F’s boundary coherence requirements to multi-agent AI systems

-----

## Status and Next Steps

**Framework status:** Working paper, Version 0.1

**Development rationale:** Formal submission is deferred pending completion of the framework’s mathematical foundation. The state machine specification, the logical layer dependencies, the tractability scoring, and the coherence scoring model require grounding in discrete mathematics, probability and statistics, control theory, and formal methods before the framework’s formal claims can be defended at the level a technically rigorous venue demands. The conceptual structure documented here is stable and is intended to guide that formalization rather than precede it.

**Mathematical formalization:** The state machine specification, trajectory dynamics, and coherence scoring model have identified formalization targets in control theory and formal methods. Full formalization is in progress and will be documented in subsequent versions.

**Planned venues:** STAMP Workshop (MIT), SafeComp, and Safety Science (Elsevier), in that sequence, following mathematical foundation completion.

**Future work:**

- Formal state transition verification (TLA+/Alloy)
- Graph-theoretic representation of coordination architectures
- Empirical validation across an extended case corpus, including survivor and recovery cases sampled on indicators rather than outcomes (see Validation and the Selection Problem)
- Proxy construction methodology for pre-adoption historical data — closure events reconstructed from waiver records, anomaly dispositions, and investigation testimony
- Runtime implementation as digital twin monitoring layer
- Organizational field studies of CCL-F adoption
- Probabilistic coherence scoring model
- Causal inference framework for intervention point claims

*The author’s development roadmap — mathematical foundation sequencing, outreach, and program targeting — is maintained separately and is not part of this document.*

-----

## References

[1] Leveson, N.G. (2012). *Engineering a Safer World: Systems Thinking Applied to Safety.* MIT Press.

[2] Malone, T.W., & Crowston, K. (1994). The interdisciplinary study of coordination. *ACM Computing Surveys, 26*(1), 87-119.

[3] Weick, K.E. (1995). *Sensemaking in Organizations.* Sage Publications.

[4] Columbia Accident Investigation Board. (2003). *Report of the Columbia Accident Investigation Board, Volume I.* NASA.

[5] Presidential Commission on the Space Shuttle Challenger Accident. (1986). *Report of the Presidential Commission on the Space Shuttle Challenger Accident.* U.S. Government Printing Office.

[6] Vaughan, D. (1996). *The Challenger Launch Decision: Risky Technology, Culture, and Deviance at NASA.* University of Chicago Press.

[7] Joint Authorities Technical Review. (2019). *Boeing 737 MAX Flight Control System: Observations, Findings, and Recommendations.* October 11, 2019.

[8] Select Bipartisan Committee to Investigate the Preparation for and Response to Hurricane Katrina. (2006). *A Failure of Initiative: Final Report.* U.S. House of Representatives.

[9] Vaughan, D. (1999). The dark side of organizations: Mistake, misconduct, and disaster. *Annual Review of Sociology, 25,* 271-305.

[10] National Commission on the BP Deepwater Horizon Oil Spill and Offshore Drilling. (2011). *Deep Water: The Gulf Oil Disaster and the Future of Offshore Drilling.* U.S. Government Printing Office.

[11] Leveson, N.G., & Turner, C.S. (1993). An investigation of the Therac-25 accidents. *IEEE Computer, 26*(7), 18-41.

[12] National Diet of Japan Fukushima Nuclear Accident Independent Investigation Commission. (2012). *The Official Report of the Fukushima Nuclear Accident Independent Investigation Commission.* National Diet of Japan.

[13] Thomas, J., & Leveson, N.G. (2018). *STPA Handbook.* MIT PSAS.

[14] Weick, K.E., & Sutcliffe, K.M. (2007). *Managing the Unexpected: Resilient Performance in an Age of Uncertainty* (2nd ed.). Jossey-Bass.

[15] Beer, S. (1972). *Brain of the Firm.* Allen Lane.

[16] Russell, S. (2019). *Human Compatible: Artificial Intelligence and the Problem of Control.* Viking.

[17] Gabriel, I. (2020). Artificial intelligence, values, and alignment. *Minds and Machines, 30*(3), 411-437.

[18] RTCA. (2011). *DO-178C: Software Considerations in Airborne Systems and Equipment Certification.* RTCA.

-----

## Changelog

**Version 0.1 — June 2026**

Initial working release. Establishes the full CCL-F architecture:

- Five-layer stack: architecture validity (Layer 0), coordination operation (Layer 1), coordination evaluation semantics (Layer 2), coordination dynamics (Layer 3), runtime realization (Layer 4)
- The Architecture Precondition (formerly Rule Zero) and the three-part architecture void taxonomy (AP-A stewardship void, AP-B channel collapse, AP-C boundary incoherence) — renamed from “Rule Zero” to signal categorical distinction from the operational rules and adopt terminology natural to government contracting and systems engineering contexts
- AP.1 expanded with AP.1a (Active Stewardship) and AP.1b (Stewardship Succession) — named successor a formal precondition; steward vs. owner terminology note added to AP.1 and Key Definitions
- Nine operational rules ordered by constraint level, with Rules 1-3 covering the epistemic foundation, Rules 4-6 covering ownership and decision architecture, and Rules 7-9 covering systemic learning and structural updating
- Rule 1 renamed from “Restore Clarity First” to “Signals Needed for Responsible Action Are Visible” and repositioned as the foundational epistemic rule
- Rule 3 renamed to “Interpretive Stability Precedes Execution” — eliminating the false assumption of prior clarity and reframing stability as a condition to be achieved rather than restored
- Rule 5 expanded with R5.1 (static matching) and R5.2 (dynamic co-evolution of responsibility, authority, and benefits)
- Rules 8 and 9 ordered per constraint level: systemic updating (Rule 8) governs stewardship distribution (Rule 9)
- Framing signal added as a sixth signal type with formal definition and escalation trigger
- Closure quality taxonomy: four closure types (evidence, authority, role-switch, authorization) tracked as categorically distinct; Role-Switch Closure formally defined, replacing the eponymous Lund Mechanism; Authorization Closure, Continuity Pressure Mechanism, and Provisional Continuation added as structural mechanism definitions
- Loop Exit Taxonomy added to Layer 2 — fourteen exit types defined with layer assignments, exit obligations, and case notes for whistleblower, legal, and key person exits
- Layer 3 (Coordination Dynamics) established — groups the Distributed Closure Constraint, Loop Tractability Assessment, Coordination Trajectory, and Revision Rigidity / Trajectory Lock as a distinct layer addressing the limits and directional evolution of closure, separate from the static evaluation semantics of Layer 2; Runtime Realization renumbered to Layer 4
- Distributed Closure Constraint (Layer 3) — introduces four closure states (local closure, attempted closure, false closure, globally unresolved distributed state) and the invariant that closure authority is bounded by agent autonomy
- Loop Tractability Assessment (Layer 3) — introduces controllability and leverage as formally derived tractability dimensions, four tractability quadrants, and time sensitivity as a recognized but not yet formalized third dimension
- Revision Rigidity and Trajectory Lock (Layer 3) — replaces “Commitment Lock” with a two-term architecture distinguishing the progressive process (revision rigidity) from the terminal condition (trajectory lock); introduces the four operations of genuine closure; names seven sources of revision rigidity accumulation; reframes the Challenger authorization as structural revision capacity failure; introduces the Revision Capacity Remaining index. Coordination Trajectory formalizes trajectory as a distinct analytical dimension alongside state, with three constraints (conditional, observable, reversible)
- Loop Entanglement added to Layer 3 — four-level entanglement spectrum (mutual influence, mutual constraint, mutual interference, deadlock); three failure modes (false closure cascade, indefinite deferral, authority override cascade) with dependency dissolution exit defined as the categorically distinct valid resolution pathway; Challenger and Boeing 737 MAX cases; registration requirement as Architecture Precondition obligation
- Closure-Resistant Loop added to Layer 3 — reinterpretation operator R formally defined; activation condition stated (K_closure > K_reinterpretation); distinguished from ordinary open loops and from the Continuity Pressure Mechanism; accountability intervention logic defined
- Commitment State Machine (Layer 4) specified with recovery transitions out of escalated and suppressed, reopen transitions from all three closed states under mandatory logging (no silent reopening), and the fourteen Layer 2 exit types integrated as recorded states with re-entry paths for recoverable and delegated exits; closed states defined as stable but not terminal
- Narrative Coherence / Operational Coherence / ΔC added to Coherence Score section — distinguishes C_n from C_o; defines the divergence measure ΔC as the measurable pathology of closure-resistant drift; Challenger cited as canonical case
- Central Claims expanded from four to eight, each labeled by epistemic status (framework commitment, empirical, or mixed), with each empirical claim stating its prediction and disconfirmation condition — Claim 5 formalizes the Distributed Closure Constraint; Claim 6 the Loop Tractability Assessment; Claim 7 Revision Rigidity and Trajectory Lock; Claim 8 Coordination Trajectory, identified as the framework’s central testable claim
- Validation and the Selection Problem section added — names the retrospective-fitting liability, defines survivor and recovery negative-case requirements (including the within-organization NASA scrub comparison set), establishes the indicator-sampled corpus design rule, and states the proxy-construction constraint for pre-adoption historical data
- Corrigibility added to Key Definitions — defined as preserved revision capacity under error, not absence of error; linked to revision rigidity, trajectory lock, and the integrating slogan
- Mathematical formalization targets noted in Status section — control theory and formal methods identified as the primary formalization tracks; detail maintained in the private development roadmap
- Executive Summary updated with integrating slogan: “A coordination system becomes dangerous when its mechanisms for preserving coherence overpower its mechanisms for revision. Coherence is healthy only when it remains corrigible.”
- Steward, Stewardship Succession, and Loop Exit added to Key Definitions; Commitment Layer, Ambiguity Debt, and Responsibility-Authority-Benefits Drift added to Key Definitions; Key Definitions reordered into logical encounter sequence
- Full inline citation apparatus added across all empirical claims and case references (18 sources)
- AI Applications section added covering signal classification, behavioral specification, and The Architecture Precondition as deployment prerequisite
- Failure taxonomy expanded to include AI deployment as an emerging case
- All rules brought to consistent structure: What it requires, How it fails, Why it matters, What to do, Cases
- Executive Summary, Overview, and Layer 1 introduction rewritten for readability
- Author’s development roadmap (mathematical foundation sequencing, outreach, program targeting) maintained as a separate private document, not part of this release

-----

*© 2026 Morgan Landry, Waterside Net Solutions. CCL-F Project.*
*Licensed under CC BY-NC-ND 4.0 (<https://creativecommons.org/licenses/by-nc-nd/4.0/>). Framework under active development — please cite the version number when referencing.*