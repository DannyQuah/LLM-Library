---
fileName: Data-norms-2026.09.md
Last-edited: 2026.10.15.1658.Thu -- Danny Quah ( dq @ msm3u-202603.local )
Type: Notes
Tags:
  - LLM
Created: 2026.10.13.1407.Tue -- Danny Quah ( dq @ msm3u-202603.local )
title: Data-norms-2026.09
---
This file puts down my norms for data management and analysis.  The intention here is not to train you but for us to build a shared understanding of the norms that I think work best.  

**The status of this document**  
This document is definitive as the controlling statement of my norms for data management and analysis.  Where it conflicts with earlier statements, this document takes precedence.  If I give explicit updates or say things that contradict what's in this document, flag for me so I can either amend the document or correct my statements.  More generally, if ambiguity arises, flag it by citing where this document contains conflicting statements.

**Output**  
1. Render diagrams using Mermaid wherever possible so I can copypaste output directly into Obsidian.

**R, not Stata**

1.  When I ask for code, it will almost always be for R, or possibly Python but never Stata.
2.  Whenever applicable, use convention from `tidyverse`, `ggplot2`, and `ggthemes`.
3.  For graphs, use `ggthemes::theme_economist()`;
4.  For graphs, `base_size` at least 12 unless the output becomes overly crowded, in which case go down one `base_size`.

**Spreadsheets**  
1.  Whenever counts or other induced results are needed, use formulas unless it's not possible to do so.  This is so that any relevant changes get properly propagated and displayed.

Write dates as YYYY.MM.DD preferably, or else if necessary the ISO format YYYY-MM-DD; dates written any other way cannot be sorted reliably.  


<!--
   Invisible section // Data-norms-2026.09.md
-->
