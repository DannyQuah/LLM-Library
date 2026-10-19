---
fileName: Incremental-checkpoints.md
Last-edited: 2026.10.18.1112.Sun -- Danny Quah ( dq @ mbpm5-202603.local )
Type: Notes
Tags:
  - economicDiplomacy
Created: 2026.10.18.1107.Sun -- Danny Quah ( dq @ mbpm5-202603.local )
title: Incremental-checkpoints
---
Rather than attempting the entire search in one execution, organise it into bounded batches.

|Stage|Work|Resource-saving approach|
|---|---|---|
|1. Source discovery|Identify candidate reports|Search by year, jurisdiction, and instrument; reuse results|
|2. Event verification|Check dates, actions, source text|Retrieve full documents only for promising candidates|
|3. Coding|Apply 3AsPlus categories|Process verified records in batches|
|4. Interim results|Search 60-day follow-ups|Prioritise confirmed events; avoid duplicate settlement searches|
|5. Integration|Update workbook|Deduplicate by stable IDs; recalculate formulas once per batch|

Each batch saves its results and search log. Subsequent batches resume from the last completed checkpoint rather than repeat earlier searches.

<!--
   Invisible section // Incremental-checkpoints.md
-->
