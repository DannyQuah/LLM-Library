---
fileName: 3AsPlus-US-trigger-first-LLM-search-instruction-script-v1.0.md
Version: 1.0
Last-edited: 2026.10.14.1618.Wed -- Danny Quah ( dq @ msm3u-202603.local )
Status: Trigger-first collection instructions
Created: 2026.10.14.1200.Wed
title: 3AsPlus-US-trigger-first-LLM-search-instruction-script-v1.0
---
# Trigger-first search: US economic statecraft and exposed Asian Third Nations

## Controlling documents
Read and follow `3AsPlus-category-coding-v1.1.md`, `Interim-Results-coding-v1.1.md`, `3AsPlus-sources-v1.0.md`, and **`3AsPlus-US-trigger-output-format-v1.0.md`**. Use the same integrated workbook and stable IDs as the response-first search. The output-format document alone controls tabs, fields, formula conventions, and QA.

## Search objective and scope
Build an independent census of identifiable US economic-statecraft trigger actions **from January 2000 to the collection date** across (1) trade policy, (2) technology controls, (3) financial sanctions, and (4) investment restrictions. Include restrictions, threats, conditional inducements, and cooperative offers when documented as external economic statecraft; exclude ordinary domestic macroeconomic measures whose foreign spillovers are incidental. Record distinct dated actions and group successive stages under `trigger_episode_id`.

For each trigger, identify potentially exposed jurisdictions among ASEAN member states, Japan, South Korea, India, and Australia. Record the documentary exposure mechanism and confidence, including indirect exposure to actions nominally targeted at China or another country. **Do not infer that every Asian country is exposed.** Construct one Trigger Exposure cell per documented trigger x jurisdiction. Search each exposed jurisdiction symmetrically for Acquiescence, Adaptation, Aggregation, Resistance, and OTHER, including possible absence of a discovered response. A completed search with no response is `response_found=NO`, not proof of real-world silence; an incomplete search is `UNDETERMINED`.

## Search procedure
1. Construct a dated US-action list from official sources: USTR, White House, BIS, OFAC, Federal Register, Treasury Investment Security, USITC, State Department, and other relevant agencies. Check independent reporting for implementation, targets, and disputes. Separate announcements from legally operative actions.
2. Deduplicate by substantive action and group stages into episodes. Assign stable `us_trigger_id` and `trigger_episode_id`. Preserve the source and magnitude.
3. Identify exposed jurisdictions using explicit coverage, supply-chain, financial, or investment mechanisms supported by source evidence. Record `exposure_type` and `exposure_confidence` before searching for responses.
4. For every exposed jurisdiction, run the same predefined battery of category-neutral, 3AsPlus, and trigger-specific searches, varying year, country, language, and official/independent source. Record exact queries and completed versus partial search coverage.
5. Verify each discovered government/regulatory response, classify strategies non-exclusively, and connect it to the trigger via Trigger-Event Links. Reuse an existing response event ID if previously found response-first; set `discovery_route=BOTH`. A contextual/weak link does not by itself establish a positive trigger-conditioned response.
6. Search subsequent US and Third-Nation developments through day 60 and code the interim-results protocol. Identify shared settlements and do not treat repeated event rows as independent US concessions.
7. Preserve genuinely searched exposure cells with no qualifying event; retain unsearched and uncertain cells with their correct status. Do not propagate an ASEAN statement as separate member-state responses.

## Coverage and stopping
Unlike response-first discovery, a trigger-first census is not complete merely upon finding 90-100 response events. Work in bounded, predeclared batches (e.g., calendar years x modality), report completed batches, and stop when the assigned batch is complete or leads are exhausted. If an external run limit is imposed, stop transparently with remaining triggers/exposure cells marked partial/not started. Report counts of trigger actions, episodes, exposed jurisdiction cells, complete cells, cells with discovered responses, and no-response-found cells, separately from event counts. Do not claim a population response rate without the appropriate completed exposure-cell denominator.

## Deliverable
Merge into the integrated workbook and return it according to **`3AsPlus-US-trigger-output-format-v1.0.md`**, including search log, coverage caveats, source-family concentration, and explicit uncertainty. No independent ad hoc output table.

<!--
   Invisible section // 3AsPlus-US-trigger-first-LLM-search-instruction-script-v1.0.md
-->
