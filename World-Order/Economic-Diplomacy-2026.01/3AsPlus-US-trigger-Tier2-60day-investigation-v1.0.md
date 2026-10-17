---
fileName: 3AsPlus-US-trigger-Tier2-60day-investigation-v1.0.md
Version: 1.0
Last-edited: 2026.10.18.0651.Sun -- Danny Quah ( dq @ mbpm5-202603.local )
Status: Proposed operational protocol; not executed
Created: 2026.10.18.0649.Sun 
Title: 3AsPlus-US-trigger-Tier2-60day-investigation-v1.0
---

# Tier 2: full 60-day outcome investigation on a predeclared stratified subsample

## Controlling documents
Follow `3AsPlus-category-coding-v1.1.md`, `Interim-Results-coding-v1.1.md`, `3AsPlus-sources-v1.0.md`, `3AsPlus-US-trigger-output-format-v1.1.md`, and `3AsPlus-Tier1-outcome-screening-v1.0.md`. This script does **not** search for new response events as its principal task; it revisits a frozen eligible frame assembled under the two Tier 1 search scripts. It never changes a strategy code merely to match a discovered outcome.

## Predeclaration hooks — fill and freeze before searching outcomes
- `sample_plan_id`: [REQUIRED unique identifier]
- `frame_snapshot_id` and `frame_as_of_date`: [REQUIRED immutable checkpoint/version]
- `eligible_unit`: [DEFAULT distinct response `event_id`; optionally sample country–episode clusters with declared weighting]
- `eligibility_rules`: [REQUIRED; default valid event, documented primary trigger link, day 60 elapsed; record excluded cases and reasons]
- `strata_variables`: [REQUIRED; proposed primary trigger modality × strategy portfolio or primary strategy; consider period and geography]
- `strata_population_counts`: [REQUIRED from frozen frame]
- `target_n_by_stratum`: [REQUIRED; set before reviewing Tier 2 outcomes]
- `selection_method`: [DEFAULT reproducible random sample within strata, with seed; alternative must be justified]
- `random_seed`: [REQUIRED integer]
- `cluster_policy`: [REQUIRED; if multiple events share a settlement or episode, decide whether to sample clusters or retain dependence and deduplicate outcomes]
- `replacement_policy`: [DEFAULT no post-outcome replacement; prespecify how ineligible or inaccessible cases are handled]
- `inclusion_probability` and `analysis_weight`: [REQUIRED when disproportionate sampling is used]
- `episode_study_supplement`: [OPTIONAL purposive cases, separately tagged and excluded from probability-sample estimates]
- `resources_and_stop_rule`: [REQUIRED bounded batches, time/verification limits, pause-and-resume policy]

**Do not begin Tier 2 searches until these fields are fixed in a dated sampling-plan record.** If some strata have too few cases, document shortfalls and revise the plan *before* inspecting outcomes. Sampling on known US-relaxation outcomes biases inference and is prohibited unless the design explicitly targets such outcomes and reports conditional selection.

## Stratification guidance
Aim for coverage across trade, technology, financial sanctions and investment restrictions; Acquiescence, Adaptation, Aggregation and Resistance (non-exclusive); major periods; and jurisdictions. Because multi-coded events cannot be uniquely assigned to several exclusive strata, predeclare a deterministic primary-strategy rule **or** stratify by mutually exclusive portfolio pattern. Report sparse cells and do not fill them artificially. Consider cluster sampling by trigger episode or shared settlement to limit repeated verification; reflect clusters in analysis.

## Full 60-day investigation workflow
1. Load frozen event, trigger, link, and Tier 1 records; confirm the relevant US baseline from dated pre-response evidence. Preserve announced versus operative policy status.
2. Construct a dated chronology from response date through response date + 60 calendar days inclusive, covering US and Third-Nation official documents and independent contemporaneous reports. Use local-language evidence where needed and log all searches, sources and inaccessible material.
3. Verify substantive US Movement (`RELAXES|UNCHANGED|TIGHTENS|MIXED|UNCLEAR|NOT_APPLICABLE`) against the pre-response baseline at day 60. `UNCHANGED` needs positive evidence, not a failed search. Preserve intervening movement in `within_window_sequence`.
4. Independently verify Third-Nation Movement, its timing (`AT_RESPONSE|AFTER_RESPONSE|BOTH|NONE_OR_NA`), and action stage. Avoid double-counting the original concession as new movement.
5. Independently code Process Status, and documentary evidence linking US and Third-Nation movement. `IMPLEMENTATION`/`MONITORING` is not US relaxation; `compromise` is a derived joint configuration, not a primitive outcome.
6. Identify shared settlements and common US decisions. Assign identical `shared_settlement_id` across affected event records and keep outcome denominators distinct at event and settlement levels.
7. Record dated, document-specific URLs, concise supporting passages, conflicting accounts, search coverage and confidence. Do not use developments after day 60 in the interim code; put them in `later_developments`.
8. Set `outcome_research_tier=TIER2_FULL` and `outcome_search_status=FULL_COMPLETE` **only when** the prescribed full investigation has been completed. If blocked, retain `PARTIAL|BLOCKED`, `full_60day_verified=0`, and explain. A completed search can still yield `UNCLEAR` where the record cannot establish movement.
9. Independently double-code a pilot of 12–15 varied cases, reconcile differences and document any coding-rule changes before processing the remaining sample. Do not silently overwrite the frozen Tier 1 record; preserve an audit trail.

## Outputs
Update the shared workbook and provide a sampling-plan manifest (frame, strata, seed, inclusion probabilities, selections), a Tier 2 completion ledger, and a resource/QA report. Distinguish weighted estimates for the probability sample from unweighted descriptive case counts. Use uncertainty intervals only when justified by the sampling design; account for episode/settlement clustering. Report missing/blocked investigations and potential nonresponse bias. Purposive episode-study supplements are not part of population estimates.

## Interpretation
Use Tier 2 to describe the joint distribution of US and Third-Nation movement and process status over a common 60-day horizon. This can strengthen **descriptive Proposition 3**, but cannot establish causal Great-Power elasticity. Do not infer causation from temporal order, official claims, or differences across strategies.
