---
fileName: 3AsPlus-US-trigger-output-format-v1.0.md
Version: 1.0
Last-edited: 2026.10.14.1559.Wed -- Danny Quah ( dq @ msm3u-202603.local )
Status: Shared workbook specification for response-first and trigger-first collection
Created: 2026.10.14.1200.Wed 
Title: 3AsPlus-US-trigger-output-format-v1.0
---
# 3AsPlus: Integrated output workbook specification

## Purpose and fundamental counting rule
Both search routes populate **one integrated workbook**, not separate incompatible datasets. The response-side census finds Third-Nation actions and traces US impulses; the trigger-first census finds US impulses and searches systematically across exposed jurisdictions, including adequately searched cells with no discovered response. These are different discovery designs; their completeness must not be conflated. Never claim that the US Triggers tab is a completed US-trigger census simply because response-first work populated it.

**Units are distinct:** US trigger action, US trigger episode, trigger–jurisdiction exposure cell, Third-Nation response event, underlying policy action, response policy package, trigger–event link, and shared settlement. Give each a stable identifier. Do not treat counts of these as interchangeable. One policy package can have several event rows; one trigger can elicit many responses; one response can link to several triggers; several responses can share a single settlement.

**Scope:** ASEAN member states, Japan, South Korea, India, and Australia; January 2000 to date of collection. Record search-period coverage explicitly. Regional blocs are distinct actors and must not be automatically replicated across member countries.

**Workbook conventions:** One header row per tab; one observation per row; ISO `YYYY-MM-DD` dates as genuine spreadsheet dates; stable snake_case field names; no merged cells in data tables; binary codes 0/1 only when established; blanks for missing, not zeros; controlled categorical codes exactly as specified. Include direct verifiable source URLs and supporting passages. Formulas wherever possible for derived counts, indicators, dates, and summaries. Freeze header rows, enable filters, and preserve an audit trail. Unique identifiers must not depend on row number, sorting, or formula recalculation.

## Worksheet 1: Events (one substantive dated Third-Nation response event per row)
Fields in order:
`event_id`, `date`, `country_or_bloc`, `actor_name`, `actor_level` (`NATIONAL|REGIONAL_BLOC|PLURILATERAL_GROUP`), `underlying_policy_action_id`, `policy_package_id`, `action_stage` (`ANNOUNCED|FORMALLY_ADOPTED|IMPLEMENTED|WITHDRAWN`), `discovery_route` (`RESPONSE_FIRST|TRIGGER_FIRST|BOTH`), `primary_us_trigger_id` (nullable convenience field; authoritative links live in Trigger-Event Links), `acquiescence`, `adaptation`, `aggregation`, `resistance`, `other`, `other_type`, `policy_instrument`, `action_description`, `headline`, `source_outlet`, `source_family`, `source_URL`, `key_quote_for_categorization`, `classification_confidence` (`High|Med|Low`), `coding_notes`, `any_3A` (formula), `number_of_strategies` (formula; four substantive modalities, excluding OTHER), `multi_strategy` (formula, >=2 substantive modalities).

Each binary category may be 1 independently. OTHER is 1 only when all four substantive modalities are 0. Count an ASEAN-wide joint statement once as a bloc event, not ten national actions. Distinct country actions receive distinct event IDs. Separate stages of one underlying policy are linked by `underlying_policy_action_id` and should not automatically count as distinct substantive responses. A policy-package identifier links different instruments in one negotiated package.

## Worksheet 2: US Triggers (one dated substantive US action per row)
`us_trigger_id`, `trigger_episode_id`, `trigger_date`, `us_agency`, `trigger_action_stage` (`INVESTIGATION|PROPOSAL|ANNOUNCEMENT|FINAL_RULE|IMPLEMENTATION|AMENDMENT|SUSPENSION|WITHDRAWAL|OTHER`), `primary_trigger_modality` (`TRADE_POLICY|TECHNOLOGY_CONTROLS|FINANCIAL_SANCTIONS|INVESTMENT_RESTRICTIONS`), `trade_policy` (0/1), `technology_controls` (0/1), `financial_sanctions` (0/1), `investment_restrictions` (0/1), `trigger_instrument`, `trigger_mode` (`RESTRICTION|THREAT|CONDITIONAL_INDUCEMENT|COOPERATIVE_OFFER|OTHER`), `target_country_or_bloc`, `affected_countries_description`, `trigger_description`, `announced_or_effective`, `effective_date`, `baseline_policy`, `trigger_magnitude`, `trigger_source_outlet`, `trigger_source_family`, `trigger_source_URL`, `trigger_key_quote`, `trigger_confidence`, `discovery_route`, `search_coverage_status`, `coding_notes`.

The four modalities are non-exclusive; classify the primary modality once, with other applicable indicators. Keep technology export controls out of the trade-policy indicator unless an independently identifiable trade-policy instrument is also present. A US action's `trigger_episode_id` links sequential investigation, proposal, determination, implementation, and amendment stages. Do not multiply one episode into several independent shocks without reporting that counting choice.

## Worksheet 3: Trigger Exposure (one US trigger action x jurisdiction exposure cell per row)
`exposure_id`, `us_trigger_id`, `country_or_bloc`, `actor_level`, `exposure_type` (`DIRECT_TARGET|DIRECTLY_AFFECTED|INDIRECTLY_EXPOSED|UNCERTAIN`), `exposure_mechanism`, `exposure_evidence`, `exposure_source_URL`, `exposure_confidence`, `response_search_status` (`NOT_STARTED|PARTIAL|COMPLETE`), `response_found` (`YES|NO|UNDETERMINED`), `first_response_date` (derived if possible), `number_of_response_events` (formula or validated pivot), `number_of_response_packages` (distinct-ID calculation), `search_notes`.

`NO` means a documented, sufficiently complete search found no qualifying response; it does **not** prove absence of real-world response. `UNDETERMINED` applies when not searched or insufficiently searched. A bloc response is its own bloc event; do not propagate it to member-state response indicators. Exposures to the same episode across stages may be aggregated by episode ID only in analysis, not by silently deleting action-level cells.

## Worksheet 4: Trigger-Event Links (one documented trigger-response relationship per row)
`link_id`, `event_id`, `us_trigger_id`, `exposure_id` (where jurisdiction-specific and defined; nullable for bloc/complex cases), `link_role` (`PRIMARY|SECONDARY|CONTEXTUAL`), `trigger_link` (`EXPLICIT|STRONGLY_INFERRED|WEAK_OR_UNESTABLISHED`), `link_evidence`, `link_source_URL`, `link_confidence`, `coding_notes`.

Unique key is `event_id + us_trigger_id`; no duplicate links. A contextual or weak link alone does not establish a qualifying response for trigger-conditioned incidence. The default eligible link is PRIMARY/SECONDARY with EXPLICIT or STRONGLY_INFERRED evidence; report sensitivity using EXPLICIT alone. Multiple credible links are permitted without duplicating the Events row. An exposure ID is a useful bridge, not a substitute for the link's own documentary evidence.

## Worksheet 5: Interim Results (one 60-day follow-up record per Events event)
`event_id`, `us_trigger_id` (primary reference, nullable), `policy_package_id`, `shared_settlement_id`, `response_date`, `baseline_date`, `baseline_US_position`, `window_end_date` (formula = response date + 60 days), `window_completeness` (`COMPLETE|WINDOW_INCOMPLETE`), `US_movement` (`RELAXES|UNCHANGED|TIGHTENS|MIXED|UNCLEAR|NOT_APPLICABLE`), `US_movement_description`, `TN_movement` (`CONCEDES|UNCHANGED|HARDENS|RESTRUCTURES|MIXED|UNCLEAR|NOT_APPLICABLE`), `TN_movement_timing` (`AT_RESPONSE|AFTER_RESPONSE|BOTH|NONE_OR_NA`), `TN_action_stage` (`ANNOUNCED|FORMALLY_ADOPTED|IMPLEMENTED|WITHDRAWN|NO_NEW_STAGE`), `TN_movement_description`, `process_status_primary`, `process_status_secondary`, `response_link_evidence` (`EXPLICIT_CONDITIONALITY|DOCUMENTED_NEGOTIATION|TEMPORAL_ASSOCIATION|NO_DOCUMENTED_LINK|INSUFFICIENT_EVIDENCE|NOT_APPLICABLE`), `outcome_date`, `within_window_sequence`, `interim_results`, `outcome_source_URL`, `supporting_quote`, `outcome_confidence`, `search_coverage`, `later_developments`, `coding_notes`.

Process-status values: `SETTLED|IMPLEMENTATION|MONITORING|NEGOTIATION|LITIGATION|INVESTIGATION|INSTITUTION_BUILDING|NO_OBSERVED_FOLLOWUP|OTHER_PROCESS`. A compromise is **derived** from bilateral movements, not a primitive result. Implementation/monitoring does not imply US policy change. Code the day-60 disposition against the documented pre-response baseline and preserve intervening changes. Distinguish `NOT_APPLICABLE` from `UNCLEAR`, and incomplete windows from observed non-changes. Shared settlements must carry the same ID; avoid counting the same US decision repeatedly as independent relief. Follow `Interim-Results-coding-v1.1.md`.

## Worksheet 6: Summary (one formula-driven metric or cross-tab cell per row)
Include counts of distinct events, policy actions, policy packages, US trigger actions, trigger episodes, exposure cells, unique settlements; totals and shares for five category indicators, any-3A, Resistance, OTHER, multi-strategy events; pairwise overlaps; modality x strategy; strategy x US_movement; strategy x process_status; US_movement x TN_movement; response-link evidence; source-family concentration (>3 event reports); missingness, low confidence, incomplete windows, and coverage by search route. Every rate must show its denominator and exclusions. Distinguish event-weighted and distinct-settlement-weighted results. For 60-day outcomes, exclude incomplete windows from complete-window rate denominators and report them separately.

## Worksheet 7: Monthly Timeline (one calendar month per row, including zero months)
`month`, `us_administration`, `total_events`, `acquiescence_events`, `adaptation_events`, `aggregation_events`, `resistance_events`, `other_events`, `any_3A_events`, `multi_strategy_events`, `us_trigger_actions`, `us_trigger_episodes_first_seen`, `trade_triggers`, `technology_triggers`, `financial_triggers`, `investment_triggers`, `significant_events`.

Counts of each category sum its 0/1 column; a multi-coded event contributes once to **each applicable category** but once to `total_events`. Modality counts likewise overlap where multi-coded. Timeline annotations are contextual, not additional data rows. Record data-coverage limitations alongside charts; a zero event count is not proof of zero underlying activity.

## Worksheet 8: Annual Observations (one calendar year per row, including zero years)
`year`, `us_administration_or_transition`, `total_events`, `acquiescence_events`, `adaptation_events`, `aggregation_events`, `resistance_events`, `other_events`, `any_3A_events`, `multi_strategy_events`, all ten unordered pairwise intersections among `acquiescence|adaptation|aggregation|resistance|other`, `unique_policy_packages`, `unique_settlements`, `us_trigger_actions`, `us_trigger_episodes_first_seen`, `trade_triggers`, `technology_triggers`, `financial_triggers`, `investment_triggers`, `exposure_cells_searched`, `us_relaxes_events`, `us_unchanged_events`, `us_tightens_events`, `annual_highlights` (last column).

Year is based on the event date for response counts, and trigger date for trigger counts. Pairwise columns count intersections, not unique combined events; `multi_strategy_events` counts distinct events with two or more substantive strategy codes. For administrations crossing a year, retain exact dates for analysis; do not force a year to belong entirely to one administration.

## Worksheet 9: Coding Notes (one rule/variable definition per row)
`protocol`, `version`, `worksheet`, `field`, `definition`, `allowed_values`, `missing_value_rule`, `borderline_case`, `source_document`. Record versioned strategy and interim protocols, event and exposure units, deduplication, denominator definitions, link thresholds, 60-day windows, and the distinction between observed absence and incomplete discovery.

## Worksheet 10: Search Log (one search attempt or defined batch per row, including zero yields)
`search_id`, `search_date`, `discovery_route`, `search_period_start`, `search_period_end`, `country_or_bloc`, `us_trigger_id` (if trigger-first), `trigger_modality`, `strategy_focus`, `search_query`, `source_domain`, `source_family`, `language`, `candidate_results`, `accepted_events`, `rejection_reason`, `search_status` (`COMPLETE|PARTIAL|NOT_STARTED`), `access_limitations`, `search_notes`.

Retain literal queries and searches yielding no events. Record whether a given jurisdiction-trigger exposure cell has received the prescribed search battery. Do not confuse a completed *search attempt* with a completed *exposure-cell search*.

## Validation and QA
1. All event IDs unique; all trigger IDs unique; all links point to existing IDs; all referenced exposure IDs point to the same trigger and appropriate jurisdiction.
2. No duplicate `event_id+us_trigger_id` link rows; no duplicate `us_trigger_id+country_or_bloc` exposure rows unless justified by explicitly separate jurisdiction-level entities.
3. OTHER=1 implies all four substantive codes 0. Multi-coding otherwise allowed.
4. `response_found=NO` only when exposure-cell search COMPLETE and no eligible linked response exists; `YES` requires at least one eligible link.
5. No interim outcome dated after window end in the 60-day code; later developments stored separately. Window incomplete flagged for recent responses.
6. Preserve source-family normalization (Reuters syndicated elsewhere is Reuters) and flag any family with >3 event reports.
7. Formula summaries recalculate and agree with raw data; explicitly verify unique-count logic (distinct IDs), rather than summing duplicated linked rows.
8. Report discovered events separately from the population of adequately searched trigger-exposure cells; do not infer responsiveness or causal effects from response-side counts alone.

## Required outputs on each collection run
Provide the workbook, its number of new/updated unique events, triggers, exposure cells, links, and settlements; the search route and coverage; source concentration; unresolved coding issues; and a brief data-quality statement. Stop according to the invoking script's rule; never pad observations to reach a quota.


<!--
   Invisible section // 3AsPlus-US-trigger-output-format-v1.0.md
-->
