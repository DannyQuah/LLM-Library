---
fileName: Interim-Results-coding-v1.2.md
title: Interim-Results-coding-v1.2
Version: 1.2
Last-edited: 2026.10.18.Sun -- Protocol revision (3AsPlus industrial-policy expansion)
Type: Research coding protocol
Status: Operational instructions for human research assistants and LLM-assisted coding
Companion: 3AsPlus-category-coding-v1.2.md
Created: 2026.10.14.0533.Wed -- Danny Quah ( dq @ mbpm5-202603.local )
---
# Interim Results: Coding Protocol — v1.2

## A. Purpose, observation, and unit

Record **observable developments after a dated Third-Nation response** to Great-Power geoeconomic statecraft. Separately code the US position, the Third Nation's position, the status of the interaction, and the evidence connecting these developments. This is a **response-side census** of realized geoeconomic interactions, not a causal estimate of strategy effectiveness or a completed **US-trigger census**.

The primary unit is the original dated response event (`event_id`). Multiple events in one package may share a settlement; retain a `shared_settlement_id` or `policy_package_id` so they are not counted as independent US decisions. Do not infer causation from temporal ordering. Preserve the existing narrative `interim_results` field while replacing the old single categorical label with the variables below.

## B. Observation window, baseline, and time sequence

**Default window:** response date through **60 calendar days after the response**, inclusive. Record `response_date`, `baseline_date`, `baseline_US_position`, `outcome_date`, and `window_end_date`. If the window is incomplete as of coding, flag `WINDOW_INCOMPLETE` rather than pretending a full 60-day follow-up exists.

The US baseline is its **latest documented pre-response substantive position or announced policy trajectory**, not a researcher-invented counterfactual. Distinguish an announced tariff from one already in force. Where no relevant US disposition exists (for example, some multilateral institution-building), record `NOT_APPLICABLE`, not `UNCLEAR`.

**Rules:**

1. Search both US and Third-Nation official announcements and independent contemporaneous reporting through day 60.
2. Record the **end-of-window disposition relative to baseline** as the primary US Movement code; also record interim changes in `within_window_sequence` when a position changes more than once.
3. Note simultaneous announcements as a **joint package**, not an invented causal sequence of Third-Nation concession followed by US relief.
4. Do not import later implementation into the 60-day outcome. Store it in `later_developments` with a date.
5. Absence of a discovered follow-up is not evidence of no effect. Record search coverage and distinguish `UNCLEAR` from `NO_OBSERVED_FOLLOWUP`.

---

## C. US MOVEMENT

### Definition

Direction of observable **substantive US policy movement** on the relevant geoeconomic instrument or contention, measured against the documented pre-response baseline at the end of the window. This is not a causal judgment.

### Values and observable forms

| Code | Operational definition | Examples |
|---|---|---|
| `RELAXES` | US withdraws, lowers, suspends, exempts, or declines an operative or announced restriction or demand. | Lowers a threatened tariff, grants exemption, suspends sanction, terminates an investigation without action. |
| `UNCHANGED` | US substantive position remains materially in place. | Existing tariff continues, licensing rule unchanged, announced investigation proceeds without new restrictions. |
| `TIGHTENS` | US adds or intensifies substantive restrictions or demands. | Raises tariff, broadens sanction, adds an export-control restriction. |
| `MIXED` | US substantively relaxes one element while tightening another in the same interaction. | Replaces a tariff with a restrictive quota, plus other material changes. |
| `UNCLEAR` | Available evidence does not establish direction of US movement despite a relevant US decision being potentially observable. | Contradictory accounts, no reliable baseline. |
| `NOT_APPLICABLE` | No meaningful bilateral US policy disposition is defined for this response. | Non-US coalition builds a new institution without seeking US action. |

### Coding rules

- Code **direction**, not the size or welfare effect of the change; separately record rates, quotas, and other magnitudes.
- Lowering a threatened 25% tariff to 15% is `RELAXES` relative to the *announced threat*, even if 15% remains restrictive. Note that baseline explicitly.
- US relaxation accompanied by large Third-Nation concessions is still `RELAXES` here; concessions belong under Third-Nation Movement.
- A procedural step in an investigation or WTO case is not automatically `TIGHTENS`; record its process status separately unless substantive restrictions/demands intensify.
- Do not automatically treat negotiation, public praise, or a promise to review as relaxation.
- If US moves from relaxation to renewed tightening during the window, code the day-60 disposition relative to baseline and record the sequence.

### Borderline cases

**Tariff exchanged for quota:** If the replacement materially restricts access, `MIXED` may be appropriate; describe both instruments and avoid implying that the outcome is unambiguously more liberal.

**Formal acceptance of compliance:** Code `RELAXES` if Washington demonstrably withdraws or declines a threatened sanction; otherwise the acceptance may change Process Status without changing substantive policy.

**No published US reaction:** Use `UNCLEAR` if a US reaction is relevant but unverified; `NOT_APPLICABLE` if no US reaction is an appropriate outcome object.

---

## D. THIRD-NATION MOVEMENT

### Definition

Direction of the responding state's substantive policy, commitment, or institutional change relative to its own documented baseline. This is **distinct from the original 3AsPlus strategy code**. Do not re-count the initial response as a new subsequent action.

### Values and observable forms

| Code | Operational definition | Examples |
|---|---|---|
| `CONCEDES` | Makes or implements substantive accommodation of the Great Power's demand. | Tariff reduction, promised purchases, new reporting commitment. |
| `UNCHANGED` | Maintains substantive position, without a newly observed accommodation, hardening, or restructuring. | Keeps existing restrictions or legal position. |
| `HARDENS` | Strengthens opposition or countermeasures, or withdraws accommodation. | Retaliatory tariff, explicit refusal of further concessions. |
| `RESTRUCTURES` | Changes domestic capabilities or external arrangements without direct concession or countermeasure on the contested axis. | Resilience programme, alternative payment arrangement, new non-US institutional partnership. |
| `MIXED` | Several distinct directional changes are inseparable within the same coded interaction. | New concession plus independent restructuring. |
| `UNCLEAR` | Evidence insufficient to establish the direction of movement. | Commitment not verified, contradictory accounts. |
| `NOT_APPLICABLE` | No additional Third-Nation movement is defined after a completed original action. | Fully executed action with no relevant further step. |

### Coding rules

- Record `TN_action_stage`: `ANNOUNCED`, `FORMALLY_ADOPTED`, `IMPLEMENTED`, `WITHDRAWN`, or `NO_NEW_STAGE`.
- When a concession is announced as the original response, do not describe its later implementation as a second concession event unless substantively distinct; do record implementation stage.
- `RESTRUCTURES` is not evidence of success: the programme may not yet produce resilience or outside options.
- Distinguish public policy from uncoordinated private-firm choices.
- A combined Acquiescence–Adaptation response need not receive `MIXED` unless the *movement* itself includes independently supported distinct changes.

### Borderline cases

**Initial concession only:** Preserve `CONCEDES` as the direction of the observed package if the response itself is the first movement, but mark `TN_movement_timing = AT_RESPONSE`, not `AFTER_RESPONSE`.

**Purely unchanged follow-up:** If no new Third-Nation decision is expected, `NOT_APPLICABLE` may be more accurate than `UNCHANGED`; use `UNCHANGED` when maintenance of a contested position is substantively observable.

---

## E. PROCESS STATUS

### Definition

Institutional/procedural status at the **end of the 60-day window**. It does not imply either side changed its substantive position, nor that the response was effective. This replaces the ambiguous old `implementation/monitoring` outcome label.

### Values

| Code | Definition |
|---|---|
| `SETTLED` | A substantive agreement or formal resolution has been reached. |
| `IMPLEMENTATION` | An identifiable agreement/commitment is being operationalised or verified. |
| `MONITORING` | Continuing supervisory, reporting, or verification process, without a new substantive settlement in the window. |
| `NEGOTIATION` | Bargaining or consultations continue without final settlement. |
| `LITIGATION` | Formal legal dispute proceedings continue. |
| `INVESTIGATION` | Administrative, trade-remedy, sanctions, or regulatory investigation continues. |
| `INSTITUTION_BUILDING` | A cooperative arrangement is being established or expanded outside the bilateral contention. |
| `NO_OBSERVED_FOLLOWUP` | No verifiable substantive or procedural follow-up was found within the window. |
| `OTHER_PROCESS` | A documented process not covered above; specify it. |

### Coding rules and contrasts

Record `process_status_primary` and, if warranted, `process_status_secondary`. A process may continue even when the US position relaxes. **Do not use `IMPLEMENTATION` or `MONITORING` as a proxy for US Movement.**

**Response-induced implementation example:** Third Nation accepts a demand; Washington suspends threatened penalties subject to verification. Code US `RELAXES`, Third Nation `CONCEDES`, Process `IMPLEMENTATION` or `MONITORING`, and separately assess the documentary link.

**Procedural continuation example:** Third Nation files a defence; USTR proceeds with previously scheduled hearings. Code US `UNCHANGED`, Third Nation `UNCHANGED` (or `NOT_APPLICABLE` absent further action), Process `INVESTIGATION`. Do not claim the defence had no effect.

**Institutional follow-through:** CPTPP parties proceed to signature without US participation. Code `INSTITUTION_BUILDING`; US Movement is normally `NOT_APPLICABLE`, not US failure to concede.

---

## F. EVIDENCE LINKING RESPONSE AND SUBSEQUENT MOVEMENT

### Definition

Strength of contemporaneous documentary evidence connecting the observed US action to the Third-Nation response. This is **not** causal identification.

| Code | Operational test |
|---|---|
| `EXPLICIT_CONDITIONALITY` | Official agreement or contemporaneous source expressly conditions US action on a specified Third-Nation commitment. |
| `DOCUMENTED_NEGOTIATION` | The two sides' movements are documented as elements of one negotiation or settlement, but individual causal contributions are not isolated. |
| `TEMPORAL_ASSOCIATION` | US movement follows the response, but no reliable source establishes a substantive connection. |
| `NO_DOCUMENTED_LINK` | Sources describe the developments without supporting a connection. |
| `INSUFFICIENT_EVIDENCE` | Reporting is inadequate or contradictory about the link. |
| `NOT_APPLICABLE` | No relevant US disposition exists to connect to the response. |

### Coding rules

Use the strongest level supported by **quoted or precisely cited** documentary evidence. Chronological succession alone supports no more than `TEMPORAL_ASSOCIATION`. A joint announcement is normally `DOCUMENTED_NEGOTIATION`, potentially `EXPLICIT_CONDITIONALITY` if the conditionality is actually stated. Never translate an official claim of causation into a causal research finding without additional identification.

---

## G. DERIVED INTERIM-RESULT CONFIGURATIONS

Do **not** code `compromise` as a primitive variable. Derive a readable summary from movements by both parties, supplemented by Process Status. These configurations are descriptive, not mutually exclusive success rankings.

| Derived description | US Movement | Third-Nation Movement | Interpretation |
|---|---|---|---|
| US relaxation | `RELAXES` | `UNCHANGED` or `NOT_APPLICABLE` | US changes its policy without a newly observed additional concession. |
| Negotiated accommodation | `RELAXES` | `CONCEDES` | Both sides materially move. |
| Restrictive compromise | `MIXED` | `CONCEDES` | US provides partial relief while retaining/adding significant restriction. |
| Continued contention | `UNCHANGED` | `UNCHANGED` or `HARDENS` | No observed substantive US relaxation. |
| US tightening | `TIGHTENS` | Any | US intensifies substantive restriction or demand. |
| Domestic adjustment | `UNCHANGED` | `RESTRUCTURES` | Third Nation changes itself while US policy remains substantively in place. |
| Institutional diversification | Any, including `NOT_APPLICABLE` | `RESTRUCTURES` | New external arrangements; assess their functionality separately. |
| Indeterminate | `UNCLEAR` | Any | Evidence insufficient to establish US direction. |

**Interpretation warning:** `RELAXES` and `CONCEDES` often form part of the *same announced bargain*. Do not claim that one caused the other merely because they occupy different columns.

---

## H. STRATEGY-SPECIFIC OUTCOMES AND HORIZONS

US Movement is a common comparison variable, **not** a universal measure of success.

| Strategy | Outcome objects for subsequent study | Typical horizon |
|---|---|---|
| Acquiescence | Bilateral relief, market/technology access, settlement, cost of concession | Short to medium |
| Adaptation | Reduced vulnerability, substitution, export diversification, productive resilience, fiscal costs | Medium to long |
| Aggregation | New and durable outside options, institutional functionality, policy space, dependence on particular Great Powers | Medium to long |
| Resistance | Reversal, deterrence, delay, precedent, leverage, and costs of contestation | Variable, often long |

A 60-day window is structurally better suited to bargaining than to domestic restructuring, coalition-building, or litigation. Do not interpret no US concession as failure of Adaptation or Aggregation. Preserve follow-up at 180 days or one year as separate future extensions.

---

## I. REQUIRED DATA FIELDS

| Field | Content |
|---|---|
| `event_id` | Link to original response event |
| `policy_package_id` | Identifier for related response actions |
| `shared_settlement_id` | Identifier for a common US disposition shared by several events |
| `response_date` | Date of original Third-Nation response |
| `baseline_date` | Date of latest documented pre-response US position |
| `baseline_US_position` | Specific threatened or operative US measure, including stage and magnitude |
| `window_end_date` | 60-day window endpoint |
| `window_completeness` | `COMPLETE` / `WINDOW_INCOMPLETE` |
| `US_movement` | Section C code |
| `US_movement_description` | Specific US movement or continuation; include magnitude |
| `TN_movement` | Section D code |
| `TN_movement_timing` | `AT_RESPONSE` / `AFTER_RESPONSE` / `BOTH` / `NONE_OR_NA` |
| `TN_action_stage` | Announcement, adoption, implementation, withdrawal, or no new stage |
| `TN_movement_description` | Specific Third-Nation movement or continuation |
| `process_status_primary` | Section E code |
| `process_status_secondary` | Optional second Section E code |
| `response_link_evidence` | Section F code |
| `outcome_date` | Date of latest relevant within-window development |
| `within_window_sequence` | Chronology of materially different within-window changes |
| `interim_results` | One or two factual sentences describing the interim disposition |
| `outcome_source_URL` | Direct URLs supporting outcome, preferably including both sides |
| `supporting_quote` | Brief supporting quotation or pinpoint passage |
| `outcome_confidence` | `High` / `Med` / `Low` |
| `search_coverage` | Sources, languages, and date range checked; note gaps |
| `later_developments` | Dated follow-up outside 60 days, not used in interim code |
| `coding_notes` | Borderline judgments, source conflicts, rationale |

## J. RA / LLM WORKFLOW AND QUALITY ASSURANCE

1. **Verify the original event** and the correct strategy coding under `3AsPlus-category-coding-v1.2.md`.
2. **Fix the baseline first.** Identify the dated US instrument, announced versus operative status, and measurable terms before looking for outcomes.
3. **Search symmetrically.** Examine US and Third-Nation official sources, contemporary independent reporting, and local-language sources where useful, for the full window.
4. **Create a chronology.** Record response date, simultaneous bargaining, substantive follow-ups, and the day-60 endpoint.
5. **Code each party independently.** Assign US Movement and Third-Nation Movement; do not infer one from the other.
6. **Code process independently.** `IMPLEMENTATION`/`MONITORING` do not establish a substantive change in US position.
7. **Code the evidentiary link.** Distinguish documented conditionality, negotiated coincidence, temporal association, and lack of evidence.
8. **Identify shared outcomes.** Repeated rows tied to one tariff bargain must share `shared_settlement_id` and not be treated as independent US concessions.
9. **Preserve uncertainty and source disagreement.** Do not convert missing reporting into `UNCHANGED`, no causal effect, or a negative result. Keep audit links and confidence.
10. **Version and test.** Independently double-code a varied pilot of 12–15 events; reconcile disagreements; log amendments; then apply the protocol consistently across the sample.

### Prohibitions for automated coding

- Do not invent dates, quotes, URLs, baseline policies, or inferred motives.
- Do not use a strategy label to predetermine the outcome label.
- Do not call `compromise` or `implementation/monitoring` an independent primitive outcome.
- Do not infer US concessions from favourable press language without a documented policy movement.
- Do not classify an outcome after day 60 as an interim result.
- Do not infer causality from temporal succession or official rhetoric alone.
- If evidence is insufficient, return the relevant `UNCLEAR`, `NOT_APPLICABLE`, or `NO_OBSERVED_FOLLOWUP` code with a reason.

**Research interpretation.** These codes describe *realized geoeconomic interactions* on the response side. Their frequencies reflect US impulses, Third-Nation actions, discovery/selection, and the timing of observation. Estimating responsiveness or effects requires a separately constructed US-trigger census and an appropriate research design.  


## v1.1 integration with dual search routes

Use `3AsPlus-US-trigger-output-format-v1.0.md` for the shared workbook fields and IDs. Each response event has one 60-day follow-up record, even when it links to several US triggers; identify the primary relevant baseline and explain any multi-trigger complexity. Use `shared_settlement_id` to avoid interpreting one US decision repeated across several response events as several independent concessions. The interim-results protocol applies identically to responses discovered via response-first or trigger-first search. `NO` response in a completed exposure-cell search is not an interim-results record and should not be assigned a US Movement outcome.


<!--
   Invisible section // Interim-Results-coding-v1.2.md
-->



## v1.2 integration note

The trigger taxonomy now uses `INDUSTRIAL_POLICY` (including investment restrictions) as its fourth top-level modality. This does not alter US Movement, Third-Nation Movement, process-status or 60-day outcome definitions. Japan's 2023 differentiated semiconductor alignment and Korea's 2022 resistance to IRA conditions are strategy/trigger illustrations; neither predetermines a US interim result.
