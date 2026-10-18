---
fileName: 3AsPlus-category-coding-v1.2.md
title: 3AsPlus-category-coding-v1.2
Version: 1.2
Last-edited: 2026.10.18.Sun -- Protocol revision (3AsPlus industrial-policy expansion)
Scope: Asian Third-Nation responses to US geoeconomic statecraft; extensible to other Great Powers
Status: Operational instructions for human research assistants and LLM-assisted coding
Created: 2026.10.14.0533.Wed -- Danny Quah ( dq @ mbpm5-202603.local )
---
# 3AsPlus: Category Coding Protocol — v1.2

**Purpose.** Classify observable Third-Nation strategic responses as Acquiescence, Adaptation, Aggregation, Resistance, and (only when necessary) OTHER. The 3As remain a distinct conceptual framework; Resistance tests its coverage rather than being renamed as a fourth A. The categories are non-exclusive. Do not classify outcomes as strategies.

This version preserves the original substantive definitions of Acquiescence, Adaptation, and Aggregation, while adding an operationally parallel Resistance section, a bounded OTHER residual, and rules for trigger-link strength, event boundaries, and multi-coding.


---

## ACQUIESCENCE
### Definition

A state makes a visible concession, accommodation, or commitment on the specific axis of a named Great-Power geoeconomic demand or contention, without directly contesting that demand as part of the same action.

Acquiescence may be rhetorical, procedural, regulatory, or substantive. It can involve a relatively inexpensive symbolic concession or a costly change in economic policy. Its immediate objective is to reduce friction, secure relief from threatened or existing restrictions, preserve access to markets or technologies, or avoid escalation.

Acquiescence does not necessarily imply political alignment, agreement with the Great Power's objectives, or abandonment of the Third Nation's longer-term interests. It may instead be a tactical means of preserving policy space while the state pursues Adaptation or Aggregation elsewhere.

### Observable forms

- **Purchase or investment commitments:** Agreeing to purchase specified quantities of US energy, agricultural products, aircraft, or other goods, or committing investment to the United States in response to trade demands.
- **Tariff and market-access concessions:** Reducing tariffs, eliminating non-tariff barriers, expanding import quotas, or granting preferential treatment requested by Washington.
- **Regulatory accommodation:** Revising intellectual-property, labour, digital-trade, investment, or other regulations to address identified US concerns.
- **Currency-policy commitments:** Agreeing to exchange-rate reviews, greater foreign-exchange transparency, or commitments concerning competitive devaluation.
- **Enforcement cooperation:** Strengthening rules-of-origin verification, transshipment inspections, export-control enforcement, or other measures in response to specific US demands.
- **Procedural or symbolic concessions:** Agreeing to consultations, reviews, monitoring, reporting, or negotiating frameworks that directly address the Great Power's stated contention.

### Signal language

"Agreed to," "pledged to," "committed to," "offered concessions," "will increase purchases of," "will reduce tariffs," "committed to review," "accepted conditions," "undertook reforms," "agreed to strengthen enforcement," "in exchange for tariff relief."

These expressions are search indicators, not sufficient evidence of Acquiescence by themselves.

### Coding rules

Code `Acquiescence = 1` when there is verifiable evidence of an identifiable government or regulatory commitment or action addressing a specific, documented Great-Power demand.

The coding requires three elements:

1. **Identifiable contention:** A named US measure, demand, threat, investigation, or negotiating condition.
2. **Responsive concession:** An observable commitment or change on that same axis of contention.
3. **Accommodation rather than direct opposition:** The action seeks to accommodate the demand rather than reject or counter it.

The concession need not succeed in securing US relief. Acquiescence describes the Third Nation's behaviour, not the Great Power's subsequent response.

A concession may be announced before implementation. Record the commitment when announced, and separately record implementation if it constitutes a substantively distinct action.

Acquiescence can coexist with Adaptation and Aggregation. A government may concede tariff access to Washington while restructuring domestic industries and negotiating alternative trade arrangements with other countries.

### Differentiated versus convergent Acquiescence

When a documented US demand or strategic understanding is followed by a substantive Third-Nation accommodation on the same axis, code Acquiescence even if national controls differ in destination coverage, re-export reach, person-based controls, legal basis, or public presentation. Record `acquiescence_form=CONVERGENT` where instruments substantially match; `DIFFERENTIATED` where the common objective is documented but implementation meaningfully differs; `UNCLEAR` where evidence does not establish the form. A public denial of following the United States is material counterevidence to assess, **not** a veto; neither apparent technical similarity nor US praise alone suffices to prove acquiescence.

**Illustrative adjudication — Japan, 2023 semiconductor equipment:** Evaluate the reported January 2023 US–Japan–Netherlands understanding alongside Japan's subsequent controls on 23 categories of semiconductor-manufacturing equipment, and Japan's destination-neutral framing and differences from US re-export/person controls. If contemporaneous sources establish the specific US request and Japan's responsive commitment, code `acquiescence=1`, `acquiescence_form=DIFFERENTIATED`, with a reasoned evidentiary link and documented qualifications. Do not infer Aggregation from cooperation with the pressuring Great Power. This is a coding illustration, not a substitute for source verification in a collection run.

### Exclusions and borderline cases

**1. Negotiation without concession.** Entering negotiations, requesting tariff relief, or expressing willingness to discuss US concerns is not sufficient unless the state makes an identifiable accommodation or commitment.

**2. General diplomatic goodwill.** Statements about friendship, partnership, or the importance of bilateral trade do not qualify without a connection to a specific demand.

**3. Domestic reform without a named demand.** A regulatory reform undertaken independently to improve competitiveness or resilience is more appropriately classified as Adaptation.

**4. Compliance with international obligations.** Implementation of an adverse WTO ruling is not automatically Acquiescence to US economic statecraft. Code Acquiescence when the evidence establishes a specific responsive concession to US pressure; otherwise record the legal-compliance mechanism separately.

**5. Simultaneous concession and resistance.** A policy package may contain both. Where possible, separate substantively distinct actions and code each appropriately. If the same indivisible action contains both accommodation and explicit opposition, document both and permit multiple coding rather than forcing a single interpretation.

**6. Costliness is not decisive.** A small symbolic concession and a substantial investment commitment can both constitute Acquiescence. Their economic significance should be assessed separately from classification.

---

## ADAPTATION

### Definition

A state undertakes domestic economic, institutional, or regulatory restructuring to reduce its vulnerability to present or future Great-Power geoeconomic pressure.

Adaptation changes the Third Nation's own capabilities, production structure, institutions, or economic dependencies rather than seeking directly to change the Great Power's contested policy. Its immediate objective is to preserve economic performance, increase resilience, reduce exposure to coercion, or improve the state's ability to withstand subsequent disruptions.

Adaptation may be prompted by a specific US action or by the broader expectation that geoeconomic restrictions will recur. It does not require an identifiable US concession or a subsequent change in US policy.

Adaptation is principally a domestic strategy. It differs from Aggregation because it does not require coordinated action with another state.

### Observable forms

- **Industrial restructuring:** Subsidies, tax incentives, industrial-policy programmes, or restructuring assistance intended to strengthen domestic production capabilities.
- **Supply-chain diversification:** Policies encouraging alternative suppliers, domestic sourcing, additional production locations, or reduced dependence on vulnerable inputs.
- **Export-market diversification:** Government programmes helping domestic firms develop markets beyond the United States or other concentrated export destinations.
- **Domestic capability-building:** Investments in semiconductor production, technology, infrastructure, skills, research, or other capabilities that reduce strategic dependence.
- **Stockpiling and strategic reserves:** Government programmes to accumulate critical materials, energy supplies, or other inputs exposed to geopolitical disruption.
- **Financial resilience:** Domestic financial-market development, regulatory adjustments, reserve-management changes, or payment-system investments intended to reduce exposure to external financial restrictions.
- **Institutional preparedness:** Establishing domestic task forces, monitoring mechanisms, contingency arrangements, or regulatory capacities to anticipate and manage geoeconomic disruptions.

### Signal language

"Reduce reliance on," "de-risk," "build resilience," "diversify away from," "reshoring," "nearshoring," "stockpile," "strengthen domestic capacity," "support affected industries," "reduce exposure," "develop alternative markets," "increase self-sufficiency," "prepare for future disruptions."

Again, these are search indicators rather than sufficient evidence.

### Coding rules

Code `Adaptation = 1` when there is verifiable evidence of an identifiable domestic government, central-bank, regulatory, or authorised industry-body action intended to reduce economic vulnerability or strengthen resilience in the face of Great-Power geoeconomic pressure.

The coding requires three elements:

1. **Domestic action:** An identifiable policy, programme, institutional reform, or commitment undertaken within the responding state.
2. **Resilience mechanism:** A plausible and documented connection between the action and reduced vulnerability, increased flexibility, or improved capacity to withstand disruption.
3. **Geoeconomic context:** Evidence linking the action to a specific US measure or to a clearly identified class of Great-Power geoeconomic risks.

The action need not be explicitly directed against the United States. Indeed, Adaptation ordinarily seeks to make the state less vulnerable regardless of whether Washington changes its policy.

The action also need not achieve its intended objective within the observation window. Adaptation describes the strategy undertaken, not demonstrated resilience.

Adaptation may coexist with Acquiescence. A government might accept US export-control requirements while separately investing in domestic technological capabilities.

### Exclusions and borderline cases

**1. Compliance masquerading as restructuring.** Domestic legal or regulatory changes made principally to satisfy a specific US demand should normally be coded Acquiescence, even if they involve substantial institutional change. Add Adaptation only when the evidence supports an independent resilience-building objective or mechanism.

**2. Ordinary industrial policy.** Subsidies, infrastructure investments, and industrial development programmes are not automatically Adaptation. There must be evidence connecting them to geoeconomic vulnerability or anticipated disruption.

**3. Private commercial decisions.** A firm's independent decision to relocate production, diversify suppliers, or change export markets is not itself Third-Nation economic diplomacy. Include it only when the coding universe permits industry-body responses or when identifiable public policy supports or directs the action.

**4. International coordination.** A jointly established regional supply-chain programme or financial arrangement normally constitutes Aggregation. A separately identifiable domestic restructuring component may additionally qualify as Adaptation.

**5. Retaliatory domestic restrictions.** Measures designed primarily to impose costs on the United States belong under Resistance, not Adaptation. Domestic measures intended primarily to reduce future vulnerability belong under Adaptation.

**6. Emergency relief versus structural resilience.** Temporary compensation to affected firms or workers may qualify when it demonstrably preserves productive capacity or facilitates adjustment. Purely compensatory transfers without an identifiable resilience mechanism should not automatically be coded Adaptation.

**7. Announcements versus implementation.** A credible, specific policy commitment may qualify before implementation. Vague aspirations to become more resilient do not.

---

## AGGREGATION  

### Definition

A state constructs, joins, or strengthens cooperative arrangements with other states to enlarge its external options, aggregate capabilities or influence, and reduce dependence on the participation, permission, or sponsorship of the Great Power whose geoeconomic conduct is at issue.

Aggregation is outward-facing coalition-building. It involves joint or plural action among two or more states, excluding the Great Power whose pressure motivates the response. Participants may be non-Great-Power peers, or may include other Great Powers.

Its immediate objective is to expand policy space through alternative markets, production networks, financial arrangements, institutional cooperation, or collective bargaining capacity.

Aggregation may complement existing US-anchored arrangements rather than replace them. It may involve conventional international-relations balancing, but does not require geopolitical opposition or a common ideology. Cooperation may instead arise because participants find the arrangement individually advantageous.

Aggregation is therefore a possible institutional expression of incentive-compatible, inadvertent cooperation. It can contribute to G-minus order when the resulting arrangement remains functional without the participation of any particular Great Power. **Aggregation, however, is not automatically G-minus.**

### Observable forms

- **Trade agreements:** Establishing or expanding regional or plurilateral trade arrangements, including agreements that proceed without US participation.
- **Financial cooperation:** Bilateral or multilateral currency swaps, local-currency settlement frameworks, payment-system interoperability, or regional financial safety nets.
- **Supply-chain partnerships:** Joint arrangements for production, critical materials, logistics, technology, or supply-chain resilience.
- **Institutional coalition-building:** Establishing or strengthening regional organisations, issue-specific coalitions, or coordinated negotiating mechanisms.
- **Joint infrastructure and technology programmes:** Cross-border projects involving shared investment, research, standards, digital infrastructure, or industrial capabilities.
- **Collective diplomatic or regulatory action:** Coordinated positions, joint representations, common regulatory approaches, or collective negotiations intended to strengthen participants' influence.
- **Strategic partnerships with other Great Powers:** Cooperation with China, the EU, Japan, India, or other major powers when such cooperation provides an alternative or complement to the US-anchored arrangement under examination.

### Signal language

"Regional alternative to," "without the United States," "deepen ties among," "new trade framework," "currency swap arrangement," "regional cooperation," "joint initiative," "collective response," "diversify partnerships," "strengthen regional integration," "regardless of Washington," "reduce dependence on a single partner."

### Coding rules

Code `Aggregation = 1` when there is verifiable evidence of identifiable joint or plural action among states that creates or strengthens external economic or institutional options in the context of Great-Power geoeconomic pressure.

The coding requires three elements:

1. **Plural participation:** At least two participating states, excluding the Great Power whose pressure is under examination.
2. **Substantive cooperation:** An identifiable joint commitment, institution, agreement, programme, or coordinated action.
3. **Strategic relevance:** Evidence that the arrangement provides an alternative, complement, hedge, or collective response to the economic relationships or institutional dependencies affected by the Great Power's conduct.

Aggregation need not be explicitly anti-US. Nor must the participants describe their actions as hedging. The strategic connection may be established through contemporaneous policy statements, documented institutional objectives, or sufficiently strong contextual evidence.

Where the relationship to US economic statecraft is inferred rather than explicitly stated, record the basis for that inference and assign lower classification confidence when appropriate.

A bilateral agreement can constitute Aggregation. Universal or ASEAN-wide participation is unnecessary.

Aggregation may coexist with Acquiescence and Adaptation. A state may make concessions to Washington while developing alternative regional markets and domestic productive capabilities.

### Exclusions and borderline cases

**1. Routine international cooperation.** Signing an agreement or holding a diplomatic meeting does not automatically constitute Aggregation. The arrangement must create or strengthen a relevant external option or collective capability.

**2. Cooperation directly with the pressuring Great Power.** A bilateral US–Vietnam agreement responding to US demands is not Aggregation when the United States is the Great Power under examination. It may constitute Acquiescence or another modality.

**3. Mere diversification of bilateral commercial relationships.** Increased private trade with another country is not sufficient. There must be identifiable government or institutional cooperation.

**4. Unilateral pursuit of new markets.** A domestic export-promotion programme directed at several foreign markets is Adaptation unless it involves substantive coordination with other governments.

**5. Pre-existing institutions.** Continuing participation in an established regional institution should not generate a new Aggregation event unless there is a substantive expansion, new commitment, or institutional change.

**6. Long-gestation agreements.** An agreement negotiated over many years should not automatically be attributed to a recent US policy shock simply because its conclusion occurs shortly afterwards. Record the relevant history and distinguish the agreement's original motivation from any subsequent geoeconomic impetus.

**7. Conventional balancing.** Joint action intended to counter US influence can qualify as Aggregation, provided it uses identifiable cooperative arrangements. Mere rhetorical alignment with another Great Power is insufficient.

**8. Dependence on another Great Power.** Cooperation with China or another Great Power may constitute Aggregation relative to US pressure, but it need not increase overall strategic autonomy. Record separately whether the arrangement replaces one Great-Power dependence with another or creates genuinely diversified options.

**9. G-minus is a separate test.** An arrangement can qualify as Aggregation even when it depends critically on China's participation, financing, or market access. Whether it remains functional without any particular Great Power is a further empirical question, not a prerequisite for Aggregation.

---

## RESISTANCE

### Definition

A state openly contests, rejects, or seeks to reverse a specific Great-Power geoeconomic action or demand, rather than conceding on the axis of contention, restructuring domestically to accommodate the pressure, or constructing alternative arrangements with other states.

Resistance involves an identifiable act of opposition directed at the Great Power's policy, demand, or claimed authority. It may employ legal, diplomatic, economic, or regulatory instruments. Its immediate objective is to defend an existing entitlement, preserve a contested policy, impose costs on the Great Power, or induce the Great Power to withdraw or modify its action. Resistance is not necessarily ineffective or normatively undesirable.

### Observable forms

- **Legal contestation:** Initiating WTO proceedings, appealing adverse rulings, or formally challenging the legality of US trade restrictions.
- **Retaliation:** Imposing counter-tariffs, reciprocal restrictions, or other economic penalties explicitly in response to US measures.
- **Diplomatic opposition:** Publicly rejecting a US demand, formally protesting an action, or announcing refusal to comply.
- **Defensive non-compliance:** Deliberately maintaining a contested policy despite an explicit US demand to change it.
- **Countermeasures:** Using economic or regulatory instruments to impose costs on the United States in response to its economic statecraft.

### Signal language

"Challenged," "contested," "rejected," "refused," "retaliated," "filed a WTO complaint," "appealed the ruling," "condemned," "opposed," "maintained restrictions despite US objections," "announced countermeasures." Signal words are search aids, not standalone proof.

### Coding rules

Code `Resistance = 1` when verifiable evidence establishes an identifiable government or regulatory action directly contesting a named US geoeconomic measure or demand. Do not require retaliation: litigation, formal diplomatic protest, and explicit refusal can independently qualify. The action must identify an object of contention; generic rhetoric does not suffice.

Resistance may coexist with the 3As, but require independent evidence for each positive code. When a government first resists and later acquiesces, record separate dated events if substantively distinct; do not retrospectively reclassify the earlier resistance.

### Exclusions and borderline cases

1. **Negotiation without opposition.** Seeking better terms is not Resistance unless it entails explicit rejection, challenge, or countermeasure.
2. **Generic criticism.** Broad statements favouring free trade do not qualify without a specific contested US action. A documented official protest can qualify even without retaliation.
3. **Litigation followed by compliance.** The initial challenge is Resistance; subsequent compliance is a distinct event and is not automatically Acquiescence unless the named-demand test is met.
4. **Non-retaliation.** A decision not to retaliate is neither Acquiescence nor Resistance by itself. Australia's April 2025 explicit criticism of US tariffs may qualify as diplomatic Resistance because of the criticism, not the restraint.
5. **Routine legal participation.** Submitting comments or evidence to a scheduled investigation is not necessarily Resistance; require a documented challenge to the measure, demand, or claimed authority.

---

## OTHER (residual)

Code `OTHER = 1` only for an observed, substantively relevant response that fits none of Acquiescence, Adaptation, Aggregation, or Resistance. Record `other_type` and a one-sentence explanation of why the four modalities do not fit. OTHER is a substantive residual, not a synonym for missing evidence, uncertainty, or non-response. Do not assign OTHER merely because the response has an unusual outcome.

---

## CROSS-CUTTING CODING CONVENTIONS

| Modality | Immediate strategic object |
|---|---|
| Acquiescence | Change the bargain through a concession on the axis of contention |
| Adaptation | Reduce domestic vulnerability to present or future pressure |
| Aggregation | Expand external options through cooperation with other states |
| Resistance | Contest the Great Power's action, demand, or authority |

### 1. Code behaviour, not eventual success

A concession remains Acquiescence if Washington refuses relief; a resilience programme remains Adaptation if economic performance later disappoints; an agreement remains Aggregation even if it subsequently fails. Do not infer motives unsupported by contemporary evidence. Interim outcomes are coded separately under `Interim-Results-coding-v1.2.md`.

### 2. Define event boundaries and implementation stages

An event is a **dated, substantively distinct government or regulatory action or commitment**. Split a policy package into separate events only where policy instruments or strategic mechanisms are distinguishable. Record `event_id` and a common `policy_package_id` for related actions. Distinguish `action_stage` as `ANNOUNCED`, `FORMALLY_ADOPTED`, `IMPLEMENTED`, or `WITHDRAWN`. A later implementation is a new event only if it represents a substantively distinct action, not mere repetition of the announcement. Do not count one package as several independent bargains in analysis.

### 3. Multiple coding and sequence

The four strategic modalities are non-exclusive. Assign each positive code only when independently supported; do not infer Adaptation merely because a concession changes domestic regulation, or G-minus merely because an arrangement is Aggregation. Where distinct actions occur sequentially, preserve their dates and identifiers rather than merging the sequence. `OTHER` should be used only when no defined modality fits the observed action.

### 4. Record the strength of the Great-Power trigger link

Keep strategy classification distinct from the strength of the connection to US pressure. Record `trigger_link` as:

| Code | Operational test |
|---|---|
| `EXPLICIT` | A contemporary source expressly identifies the US measure, demand, or risk motivating the action. |
| `STRONGLY_INFERRED` | Timing and documentary context establish a substantial link, though no source states it explicitly; explain the inference. |
| `WEAK_OR_UNESTABLISHED` | Connection is plausible but inadequately supported; retain as a candidate, not an established US-response observation. |

This is especially important for long-gestation Aggregation arrangements and anticipatory Adaptation. Record the `us_trigger`, its date (if known), and the evidence supporting the link. A general atmosphere of geopolitical competition does not establish that a particular agreement responds to a particular US action.

### 5. Sources, uncertainty, and audit trail

For every event retain: event date, country/bloc, policy-package ID, action stage, four binary modality codes plus OTHER, `other_type` if needed, trigger link, source outlet, direct source URL, short action description, supporting quotation or passage, and `classification_confidence` (`High`, `Med`, `Low`). Distinguish missing information from an observed zero. Cite primary policy documents and independent reporting when available; preserve disagreement between sources. Search keywords are discovery aids, not coding rules.

### 6. Research-assistant decision sequence

1. Identify the actor, dated action, policy instrument, and evidence.
2. Identify the US measure/demand or broader risk, and code `trigger_link`.
3. Decide whether the action is substantively distinct; assign `event_id`, `policy_package_id`, and `action_stage`.
4. Test Acquiescence, Adaptation, Aggregation, and Resistance separately; multiple 1s are permitted with independent support.
5. If all four are zero but a substantive response remains, code OTHER and explain `other_type`.
6. Record sources, confidence, uncertainties, and any sequence with prior or subsequent events.
7. Keep subsequent US and Third-Nation outcomes in the separate interim-results protocol.

### 7. Research design caution

Counts in a **response-side census** represent recorded realized geoeconomic interactions. Their time pattern reflects both the distribution of US impulses and the Third-Nation response function, as well as source discovery. They do not by themselves identify Third-Nation responsiveness or causal effects. The future **US-trigger census** is a separate research object.

## v1.1 integration with dual search routes

Use the shared workbook specification `3AsPlus-US-trigger-output-format-v1.0.md`. Apply the same strategy definitions regardless of whether an event is discovered response-first or trigger-first. Link each qualifying event to all supported triggers in `Trigger-Event Links`; do not duplicate an event when rediscovered. Record `discovery_route` and stable `underlying_policy_action_id`, `policy_package_id`, and `event_id`. A regional-bloc event is one bloc-level action; do not multiply it across member states. `Trigger Exposure` is the separate unit for documented jurisdiction exposure and completed searches finding no response. An event can be linked to multiple triggers without creating multiple event rows. `OTHER` remains substantive residual and is never a substitute for a search with no response found.


<!--
   Invisible section // 3AsPlus-category-coding-v1.2.md
-->

## Cross-protocol illustration: Korea and US industrial policy

The Korean government's 2022 opposition to the Inflation Reduction Act's discriminatory electric-vehicle tax-credit and North American assembly requirements illustrates `Resistance=1` to a US `INDUSTRIAL_POLICY` trigger, with `DOMESTIC_CONTENT` and `SUBSIDY_TAX_CREDIT` instrument details. Do not force the US measure into an investment restriction or infer Adaptation from Korea's objection alone. Separately dated Korean concessions, restructuring or coalitions require independent evidence and coding. The illustration shows that discriminatory inducements can generate opposition without a simple coercion/compliance binary.
