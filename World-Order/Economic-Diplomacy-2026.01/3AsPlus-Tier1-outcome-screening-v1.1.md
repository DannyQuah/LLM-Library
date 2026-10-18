---
fileName: 3AsPlus-Tier1-outcome-screening-v1.1.md
Version: 1.1
Last-edited: 2026.10.18.Sun -- Protocol revision (3AsPlus industrial-policy expansion)
Status: Proposed operational protocol; not executed
Created: 2026.10.18.0649.Sun 
Title: 3AsPlus-Tier1-outcome-screening-v1.1
---

# Tier 1: bounded interim-outcome screening for every qualifying response event

## Authority and purpose
This is a **provisional depth-of-search addendum** to `Interim-Results-coding-v1.2.md`. It changes the *required search effort*, **not** the meanings of US Movement, Third-Nation Movement, process status, evidence of linkage, or the 60-calendar-day outcome horizon. The full protocol remains controlling for definitions. The shared workbook is `3AsPlus-US-trigger-output-format-v1.2.md`.

Tier 1 supports a broad response-side census for strategic differentiation and dynamic complementarity. It supplies partial, clearly labelled descriptive context for Great-Power responsiveness; it is **not** a completed 60-day outcome census.

## Minimum screening per accepted event
1. Confirm the original dated action, primary trigger link, and any baseline US position **actually stated in verified contemporaneous records**. Never manufacture a baseline.
2. Review the event's original report and any linked official agreement or US decision for a simultaneous bargain, announced relief, continuing process, or documented implementation.
3. Perform a **bounded follow-up** using at least one targeted US-side and one Third-Nation-side query combining the relevant actor, instrument, and the 60-day date window. Check the most directly relevant primary document when located. Where one side's documents are unavailable, note this explicitly. Search queries and results go into Search Log.
4. Check for a shared settlement already verified for another event and reuse its ID and evidence rather than retrieve it again. A shared settlement is not an additional independent US concession.
5. Record each *positively verified* movement, dated process development, and supporting URL/quotation. Preserve `within_window_sequence` when multiple dated changes are found.
6. Stop the bounded screen once the prescribed queries and directly relevant evidence checks are completed. Escalate to Tier 2 only if the event is selected by the predeclared sampling design, not merely because it is interesting or easy to research.

## Required evidence discipline
- `RELAXES`, `TIGHTENS`, `MIXED`, `CONCEDES`, `HARDENS`, and `RESTRUCTURES` require affirmative source evidence and a defensible baseline. A contemporaneous joint bargain is not evidence of temporal causation.
- `UNCHANGED` requires **affirmative evidence** of substantive policy continuity relative to the documented baseline; an unsuccessful bounded search cannot establish it.
- `UNCLEAR` is appropriate when a relevant movement is potentially observable but not established. `NOT_APPLICABLE` means the movement is not a meaningful outcome object. Do not confuse either with `NO_OBSERVED_FOLLOWUP` (a process-status label).
- `window_completeness=COMPLETE` means 60 days have elapsed, **not** that an exhaustive 60-day search was done. `WINDOW_INCOMPLETE` means day 60 has not yet elapsed.
- Keep original `interim_results` narrative concise and factual. Do not impute an effect from sequence or publicity.

## Additional required outcome ascertainment fields
Use the columns added to `Interim Results` in the v1.1 output specification:
- `outcome_research_tier`: `TIER1_SCREEN|TIER2_FULL`.
- `outcome_search_status`: `NOT_STARTED|SCREEN_COMPLETE|FULL_COMPLETE|PARTIAL|BLOCKED`.
- `outcome_ascertainment`: `DOCUMENTED_MOVEMENT|DOCUMENTED_CONTINUITY|PROCESS_ONLY|NO_VERIFIABLE_FOLLOWUP|INDETERMINATE|NOT_APPLICABLE`.
- `screen_queries_count`, `screen_sources_checked_count`: measured nonnegative integers, not estimates.
- `full_60day_verified`: 1 **only** for Tier 2 cases with completed search through day 60; 0 for Tier 1 or incomplete cases. It is a research-completeness flag, not an outcome code.
- `screen_limitations`: what could not be checked, source gaps, or reason for stopping.
- `outcome_review_priority`: `STANDARD|UNCERTAIN_BASELINE|CONFLICTING_SOURCES|SHARED_SETTLEMENT|POTENTIAL_EPISODE_STUDY|OTHER`; a priority flag does not itself authorise Tier 2 inclusion.

## Resource instrumentation
In Search Log, record literal queries, discovery route, source family, candidate count when available, accepted records, duplicates and rejected leads. For each bounded batch record `batch_id`, `workflow_stage`, `elapsed_seconds` (only when measured), `source_fetches_count`, `documents_reused_count`, and `measurement_notes`. Token counts, billable compute, and downloaded bytes must be left unavailable unless independently measured. Do not report an estimate as an observation.

## Reporting and denominators
All response events may be included in strategy frequencies. For US disposition, report (a) the number of Tier 1 events with *positively documented* movement, (b) the number screened but unresolved, and (c) Tier 2 fully ascertained cases separately. Never treat Tier 1 unresolved events as `UNCHANGED` or include them in a complete-outcome denominator. Any Tier 1 outcome percentages must be explicitly labelled **among documented outcomes only; selection/ascertainment bias possible**. No causal interpretation.

## Checkpoint acceptance
A checkpoint is accepted only when IDs and cross-sheet links validate; searches and no-yield searches are logged; source URLs are document-specific; dates and action stages are distinct; outcome ascertainment is explicit; and unresolved outcomes remain unresolved. Preserve all previously validated records and audit changes.

## Industrial-policy and differentiated-acquiescence checks

For `INDUSTRIAL_POLICY` triggers, distinguish US subsidy or tax-credit eligibility, domestic-content conditions, procurement rules, investment incentives, and inbound/outbound investment restrictions. Record the operative instrument and its external geoeconomic mechanism. For differentiated Acquiescence (e.g., Japan 2023), preserve both documented US coordination and national departures from US rule scope; a Tier 1 screen does not turn US praise into a verified subsequent concession. Korea's IRA objection illustrates Resistance to a discriminatory inducement.
