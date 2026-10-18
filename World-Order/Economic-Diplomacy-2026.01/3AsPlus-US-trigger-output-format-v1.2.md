---
fileName: 3AsPlus-US-trigger-output-format-v1.2.md
Version: 1.2
Last-edited: 2026.10.18.Sun -- Protocol revision (3AsPlus industrial-policy expansion)
Status: Shared workbook specification for response-first and trigger-first collection
Created: 2026.10.14.1200.Wed 
Title: 3AsPlus-US-trigger-output-format-v1.2
---
# 3AsPlus: Integrated output workbook specification

## Purpose and fundamental counting rule
Both search routes populate **one integrated workbook**, not separate incompatible datasets. The response-side census finds Third-Nation actions and traces US impulses; the trigger-first census finds US impulses and searches systematically across exposed jurisdictions, including adequately searched cells with no discovered response. These are different discovery designs; their completeness must not be conflated. Never claim that the US Triggers tab is a completed US-trigger census simply because response-first work populated it.

**Units are distinct:** US trigger action, US trigger episode, trigger–jurisdiction exposure cell, Third-Nation response event, underlying policy action, response policy package, trigger–event link, and shared settlement. Give each a stable identifier. Do not treat counts of these as interchangeable. One policy package can have several event rows; one trigger can elicit many responses; one response can link to several triggers; several responses can share a single settlement.

**Scope:** ASEAN member states, Japan, South Korea, India, and Australia; January 2000 to date of collection. Record search-period coverage explicitly. Regional blocs are distinct actors and must not be automatically replicated across member countries.

**Workbook conventions:** One header row per tab; one observation per row; ISO `YYYY-MM-DD` dates as genuine spreadsheet dates; stable snake_case field names; no merged cells in data tables; binary codes 0/1 only when established; blanks for missing, not zeros; controlled categorical codes exactly as specified. Include direct verifiable source URLs and supporting passages. Formulas wherever possible for derived counts, indicators, dates, and summaries. Freeze header rows, enable filters, and preserve an audit trail. Unique identifiers must not depend on row number, sorting, or formula recalculation.

## Worksheet 1: Events (one substantive dated Third-Nation response event per row)
Fields in order:
`event_id`, `date`, `country_or_bloc`, `actor_name`, `actor_level` (`NATIONAL|REGIONAL_BLOC|PLURILATERAL_GROUP`), `underlying_policy_action_id`, `policy_package_id`, `action_stage` (`ANNOUNCED|FORMALLY_ADOPTED|IMPLEMENTED|WITHDRAWN`), `discovery_route` (`RESPONSE_FIRST|TRIGGER_FIRST|BOTH`), `primary_us_trigger_id` (nullable convenience field; authoritative links live in Trigger-Event Links), `acquiescence`, `acquiescence_form` (`CONVERGENT|DIFFERENTIATED|UNCLEAR|NOT_APPLICABLE`), `adaptation`, `aggregation`, `resistance`, `other`, `other_type`, `policy_instrument`, `action_description`, `headline`, `source_outlet`, `source_family`, `source_URL`, `key_quote_for_categorization`, `classification_confidence` (`High|Med|Low`), `coding_notes`, `any_3A` (formula), `number_of_strategies` (formula; four substantive modalities, excluding OTHER), `multi_strategy` (formula, >=2 substantive modalities).

Set `acquiescence_form=NOT_APPLICABLE` when `acquiescence=0`. `DIFFERENTIATED` denotes documented accommodation of a named US objective with materially distinct national scope, legal framing or implementation; a public denial is evidence to evaluate, not an automatic exclusion. Japan’s 2023 semiconductor-equipment controls are a candidate differentiated-acquiescence case requiring a verified US request/understanding, Japan’s action, and contemporaneous qualifications. Do not code Japan–US–Netherlands cooperation as Aggregation relative to US pressure merely because several states participated.

Each binary category may be 1 independently. OTHER is 1 only when all four substantive modalities are 0. Count an ASEAN-wide joint statement once as a bloc event, not ten national actions. Distinct country actions receive distinct event IDs. Separate stages of one underlying policy are linked by `underlying_policy_action_id` and should not automatically count as distinct substantive responses. A policy-package identifier links different instruments in one negotiated package.

## Worksheet 2: US Triggers (one dated substantive US action per row)
`us_trigger_id`, `trigger_episode_id`, `trigger_date`, `us_agency`, `trigger_action_stage` (`INVESTIGATION|PROPOSAL|ANNOUNCEMENT|FINAL_RULE|IMPLEMENTATION|AMENDMENT|SUSPENSION|WITHDRAWAL|OTHER`), `primary_trigger_modality` (`TRADE_POLICY|TECHNOLOGY_CONTROLS|FINANCIAL_SANCTIONS|INDUSTRIAL_POLICY`), `trade_policy` (0/1), `technology_controls` (0/1), `financial_sanctions` (0/1), `industrial_policy` (0/1), `trigger_instrument`, `trigger_mode` (`RESTRICTION|THREAT|CONDITIONAL_INDUCEMENT|COOPERATIVE_OFFER|OTHER`), `target_country_or_bloc`, `affected_countries_description`, `trigger_description`, `announced_or_effective`, `effective_date`, `baseline_policy`, `trigger_magnitude`, `trigger_source_outlet`, `trigger_source_family`, `trigger_source_URL`, `trigger_key_quote`, `trigger_confidence`, `discovery_route`, `search_coverage_status`, `coding_notes`.

**Industrial-policy boundary and instrument detail:** `INDUSTRIAL_POLICY` includes `SUBSIDY_TAX_CREDIT`, `DOMESTIC_CONTENT`, `PROCUREMENT_PREFERENCE`, `INVESTMENT_INCENTIVE`, `INBOUND_INVESTMENT_RESTRICTION`, `OUTBOUND_INVESTMENT_RESTRICTION`, and `OTHER_INDUSTRIAL_POLICY`. These are controlled `trigger_instrument` values (or documented combinations where more than one instrument is present), not additional top-level modality columns. Include only measures with a documented external geoeconomic mechanism (e.g., nationality or location conditions, foreign strategic-supply-chain objectives, or cross-border investment constraints). General domestic subsidies without that connection are excluded. If a measure contains separately identifiable trade and industrial-policy instruments, code both applicable binary indicators and choose a documented primary modality. All future data use the current four modalities without storing obsolete investment-restriction top-level fields or parallel historical codes.

The four modalities are non-exclusive; classify the primary modality once, with other applicable indicators. Keep technology export controls out of the trade-policy indicator unless an independently identifiable trade-policy instrument is also present. A US action's `trigger_episode_id` links sequential investigation, proposal, determination, implementation, and amendment stages. Do not multiply one episode into several independent shocks without reporting that counting choice.

## Worksheet 3: Trigger Exposure (one US trigger action x jurisdiction exposure cell per row)
`exposure_id`, `us_trigger_id`, `country_or_bloc`, `actor_level`, `exposure_type` (`DIRECT_TARGET|DIRECTLY_AFFECTED|INDIRECTLY_EXPOSED|UNCERTAIN`), `exposure_mechanism`, `exposure_evidence`, `exposure_source_URL`, `exposure_confidence`, `response_search_status` (`NOT_STARTED|PARTIAL|COMPLETE`), `response_found` (`YES|NO|UNDETERMINED`), `first_response_date` (derived if possible), `number_of_response_events` (formula or validated pivot), `number_of_response_packages` (distinct-ID calculation), `search_notes`.

`NO` means a documented, sufficiently complete search found no qualifying response; it does **not** prove absence of real-world response. `UNDETERMINED` applies when not searched or insufficiently searched. A bloc response is its own bloc event; do not propagate it to member-state response indicators. Exposures to the same episode across stages may be aggregated by episode ID only in analysis, not by silently deleting action-level cells.

## Worksheet 4: Trigger-Event Links (one documented trigger-response relationship per row)
`link_id`, `event_id`, `us_trigger_id`, `exposure_id` (where jurisdiction-specific and defined; nullable for bloc/complex cases), `link_role` (`PRIMARY|SECONDARY|CONTEXTUAL`), `trigger_link` (`EXPLICIT|STRONGLY_INFERRED|WEAK_OR_UNESTABLISHED`), `link_evidence`, `link_source_URL`, `link_confidence`, `coding_notes`.

Unique key is `event_id + us_trigger_id`; no duplicate links. A contextual or weak link alone does not establish a qualifying response for trigger-conditioned incidence. The default eligible link is PRIMARY/SECONDARY with EXPLICIT or STRONGLY_INFERRED evidence; report sensitivity using EXPLICIT alone. Multiple credible links are permitted without duplicating the Events row. An exposure ID is a useful bridge, not a substitute for the link's own documentary evidence.

## Worksheet 5: Interim Results (one 60-day follow-up record per Events event)
`event_id`, `us_trigger_id` (primary reference, nullable), `policy_package_id`, `shared_settlement_id`, `response_date`, `baseline_date`, `baseline_US_position`, `window_end_date` (formula = response date + 60 days), `window_completeness` (`COMPLETE|WINDOW_INCOMPLETE`), `US_movement` (`RELAXES|UNCHANGED|TIGHTENS|MIXED|UNCLEAR|NOT_APPLICABLE`), `US_movement_description`, `TN_movement` (`CONCEDES|UNCHANGED|HARDENS|RESTRUCTURES|MIXED|UNCLEAR|NOT_APPLICABLE`), `TN_movement_timing` (`AT_RESPONSE|AFTER_RESPONSE|BOTH|NONE_OR_NA`), `TN_action_stage` (`ANNOUNCED|FORMALLY_ADOPTED|IMPLEMENTED|WITHDRAWN|NO_NEW_STAGE`), `TN_movement_description`, `process_status_primary`, `process_status_secondary`, `response_link_evidence` (`EXPLICIT_CONDITIONALITY|DOCUMENTED_NEGOTIATION|TEMPORAL_ASSOCIATION|NO_DOCUMENTED_LINK|INSUFFICIENT_EVIDENCE|NOT_APPLICABLE`), `outcome_date`, `within_window_sequence`, `interim_results`, `outcome_source_URL`, `supporting_quote`, `outcome_confidence`, `search_coverage`, `later_developments`, `coding_notes`.

Process-status values: `SETTLED|IMPLEMENTATION|MONITORING|NEGOTIATION|LITIGATION|INVESTIGATION|INSTITUTION_BUILDING|NO_OBSERVED_FOLLOWUP|OTHER_PROCESS`. A compromise is **derived** from bilateral movements, not a primitive result. Implementation/monitoring does not imply US policy change. Code the day-60 disposition against the documented pre-response baseline and preserve intervening changes. Distinguish `NOT_APPLICABLE` from `UNCLEAR`, and incomplete windows from observed non-changes. Shared settlements must carry the same ID; avoid counting the same US decision repeatedly as independent relief. Follow `Interim-Results-coding-v1.2.md`.

## Worksheet 6: Summary (one formula-driven metric or cross-tab cell per row)
Include counts of distinct events, policy actions, policy packages, US trigger actions, trigger episodes, exposure cells, unique settlements; totals and shares for five category indicators, any-3A, Resistance, OTHER, multi-strategy events; pairwise overlaps; modality x strategy; strategy x US_movement; strategy x process_status; US_movement x TN_movement; response-link evidence; source-family concentration (>3 event reports); missingness, low confidence, incomplete windows, and coverage by search route. Every rate must show its denominator and exclusions. Distinguish event-weighted and distinct-settlement-weighted results. For 60-day outcomes, exclude incomplete windows from complete-window rate denominators and report them separately.

## Worksheet 7: Monthly Timeline (one calendar month per row, including zero months)
`month`, `us_administration`, `total_events`, `acquiescence_events`, `adaptation_events`, `aggregation_events`, `resistance_events`, `other_events`, `any_3A_events`, `multi_strategy_events`, `us_trigger_actions`, `us_trigger_episodes_first_seen`, `trade_triggers`, `technology_triggers`, `financial_triggers`, `industrial_policy_triggers`, `significant_events`.

Counts of each category sum its 0/1 column; a multi-coded event contributes once to **each applicable category** but once to `total_events`. Modality counts likewise overlap where multi-coded. Timeline annotations are contextual, not additional data rows. Record data-coverage limitations alongside charts; a zero event count is not proof of zero underlying activity.

## Worksheet 8: Annual Observations (one calendar year per row, including zero years)
`year`, `us_administration_or_transition`, `total_events`, `acquiescence_events`, `adaptation_events`, `aggregation_events`, `resistance_events`, `other_events`, `any_3A_events`, `multi_strategy_events`, all ten unordered pairwise intersections among `acquiescence|adaptation|aggregation|resistance|other`, `unique_policy_packages`, `unique_settlements`, `us_trigger_actions`, `us_trigger_episodes_first_seen`, `trade_triggers`, `technology_triggers`, `financial_triggers`, `industrial_policy_triggers`, `exposure_cells_searched`, `us_relaxes_events`, `us_unchanged_events`, `us_tightens_events`, `annual_highlights` (last column).

Year is based on the event date for response counts, and trigger date for trigger counts. Pairwise columns count intersections, not unique combined events; `multi_strategy_events` counts distinct events with two or more substantive strategy codes. For administrations crossing a year, retain exact dates for analysis; do not force a year to belong entirely to one administration.

## Worksheet 9: Coding Notes (one rule/variable definition per row)
`protocol`, `version`, `worksheet`, `field`, `definition`, `allowed_values`, `missing_value_rule`, `borderline_case`, `source_document`. Record versioned strategy and interim protocols, event and exposure units, deduplication, denominator definitions, link thresholds, 60-day windows, and the distinction between observed absence and incomplete discovery.

## Worksheet 10: Search Log (one search attempt or defined batch per row, including zero yields)
`search_id`, `search_date`, `discovery_route`, `search_period_start`, `search_period_end`, `country_or_bloc`, `us_trigger_id` (if trigger-first), `trigger_modality`, `strategy_focus`, `search_query`, `source_domain`, `source_family`, `language`, `candidate_results`, `accepted_events`, `rejection_reason`, `search_status` (`COMPLETE|PARTIAL|NOT_STARTED`), `access_limitations`, `search_notes`.

Retain literal queries and searches yielding no events. Record whether a given jurisdiction-trigger exposure cell has received the prescribed search battery. Do not confuse a completed *search attempt* with a completed *exposure-cell search*.

## Validation and QA
- Verify `acquiescence_form` is populated consistently with `acquiescence`, and that differentiated cases include both US-demand evidence and the documented implementation differences.
- Industrial-policy trigger records must identify an external economic-statecraft mechanism; retain investment restrictions as instruments, not a fifth top-level modality.

1. All event IDs unique; all trigger IDs unique; all links point to existing IDs; all referenced exposure IDs point to the same trigger and appropriate jurisdiction.
2. No duplicate `event_id+us_trigger_id` link rows; no duplicate `us_trigger_id+country_or_bloc` exposure rows unless justified by explicitly separate jurisdiction-level entities.
3. OTHER=1 implies all four substantive codes 0. Multi-coding otherwise allowed.
4. `response_found=NO` only when exposure-cell search COMPLETE and no eligible linked response exists; `YES` requires at least one eligible link.
5. No interim outcome dated after window end in the 60-day code; later developments stored separately. Window incomplete flagged for recent responses.
6. Preserve source-family normalization (Reuters syndicated elsewhere is Reuters) and flag any family with >3 event reports.
7. Formula summaries recalculate and agree with raw data; explicitly verify unique-count logic (distinct IDs), rather than summing duplicated linked rows.
8. Report discovered events separately from the population of adequately searched trigger-exposure cells; do not infer responsiveness or causal effects from response-side counts alone.

## Tiered outcome-screening extensions (v1.1)

The original ten-tab structure and fields above remain controlling. Routine collection follows `3AsPlus-Tier1-outcome-screening-v1.1.md`; full outcome investigation uses `3AsPlus-US-trigger-Tier2-60day-investigation-v1.1.md`.

## Additional fields — append to Interim Results after existing `coding_notes`
`outcome_research_tier` (`TIER1_SCREEN|TIER2_FULL`), `outcome_search_status` (`NOT_STARTED|SCREEN_COMPLETE|FULL_COMPLETE|PARTIAL|BLOCKED`), `outcome_ascertainment` (`DOCUMENTED_MOVEMENT|DOCUMENTED_CONTINUITY|PROCESS_ONLY|NO_VERIFIABLE_FOLLOWUP|INDETERMINATE|NOT_APPLICABLE`), `screen_queries_count` (integer), `screen_sources_checked_count` (integer), `full_60day_verified` (0/1), `screen_limitations` (text), `outcome_review_priority` (`STANDARD|UNCERTAIN_BASELINE|CONFLICTING_SOURCES|SHARED_SETTLEMENT|POTENTIAL_EPISODE_STUDY|OTHER`), `tier2_sample_plan_id` (nullable), `tier2_inclusion_probability` (nullable numeric), `tier2_analysis_weight` (nullable numeric).

`window_completeness` retains its existing meaning: calendar horizon elapsed vs not elapsed. **It does not imply search completeness.** `full_60day_verified=1` requires Tier 2 full completion and elapsed day 60. `NO_VERIFIABLE_FOLLOWUP` is not equivalent to `UNCHANGED`. Do not infer US or TN movement from the outcome-ascertainment label.

## Additional fields — append to Search Log after existing `search_notes`
`batch_id` (stable string), `workflow_stage` (`DISCOVERY|TRIGGER_VERIFICATION|EXPOSURE_VERIFICATION|RESPONSE_VERIFICATION|STRATEGY_CODING|TIER1_SCREEN|TIER2_FULL|WORKBOOK_QA`), `elapsed_seconds` (measured numeric or blank), `source_fetches_count` (measured integer or blank), `documents_reused_count` (measured integer or blank), `measurement_notes` (state unavailable counters, methodology and caveats).

## Sampling manifest and stratification metadata
Retain the **ten-tab workbook**. Record Tier 2 selection and design in an external, versioned `sample_plan_id` manifest; record plan ID, inclusion probability and analysis weight on sampled Interim Results rows. The manifest must specify the frozen frame, eligibility, strata, seed, target n, cluster and replacement rules, selections and exclusions. Do not add an unannounced eleventh tab or silently mix purposive cases with probability-sampled cases.

## Summary and denominator requirements
Continue all v1.0 metrics. **Separate Tier 1 positively documented dispositions, Tier 1 unresolved screens, Tier 2 fully investigated outcomes, and Tier 2 partial/blocked cases.** Every conditional probability table must identify its denominator, link threshold, observation horizon and ascertainment tier. Never treat Tier 1 outcomes as complete-case probability estimates without a selection-bias caveat. Event-weighted and distinct-settlement-weighted outcomes remain separate. For Proposition 3, reserve primary 60-day comparisons for the Tier 2 design-based sample; Tier 1 is broad descriptive context only.

## Validation additions
- `outcome_search_status=FULL_COMPLETE` implies `outcome_research_tier=TIER2_FULL`, `full_60day_verified=1`, and elapsed day 60.
- `outcome_search_status=SCREEN_COMPLETE` implies `outcome_research_tier=TIER1_SCREEN` and `full_60day_verified=0`.
- `UNCHANGED` requires documented baseline and affirmative continuity evidence, not an empty search result.
- No Tier 2 probability/weight values without a frozen sample-plan identifier.
- Search Log effort counters are measured, never fabricated; unknown is blank, not zero.
- Checkpoint updates preserve original event IDs and do not duplicate shared settlements or action stages.

## Output per run
Provide workbook, coverage, counts of new/updated distinct IDs, source concentration, tier-specific ascertainment and uncertainty, search resource metrics where measured, checkpoint identifier, and uncompleted batch scope. Avoid causal claims.

## Required outputs on each collection run
Provide the workbook, its number of new/updated unique events, triggers, exposure cells, links, and settlements; the search route and coverage; source concentration; unresolved coding issues; and a brief data-quality statement. Stop according to the invoking script's rule; never pad observations to reach a quota.


<!--
   Invisible section // 3AsPlus-US-trigger-output-format-v1.2.md
-->
