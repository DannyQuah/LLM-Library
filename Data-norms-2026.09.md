---
fileName: Data-norms-2026.09.md
Last-edited: 2026.10.18.0748.Sun -- Danny Quah ( dq @ mbpm5-202603.local )
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
1. Render diagrams using Mermaid wherever possible so I can copypaste output directly into Obsidian.  Ensure Mermaid code blocks are strictly formatted as raw code syntax so I can copy the text directly.
2. When revising Markdown scripts or updating to new versions, as far as possible retain (if found) my YAML "Last-edited: ","Created: ", and "Title: " lines; update (if found) the "Last-edited: " and "Title: " values.  However, don't create these lines if not already there.
3. For output formats (including filenames as necessary) write dates as YYYY.MM.DD preferably.  For internal usage or where it's required for interoperability (e.g., in spreadsheet data sourced elsewhere), or wherever else as necessary, choose ISO format YYYY-MM-DD when available.


**R, not Stata**

1.  When I ask for code, it will almost always be for R, or possibly Python but never Stata.
2.  Whenever applicable, use convention from `tidyverse`, `ggplot2`, and `ggthemes`.
3.  For graphs, use `ggthemes::theme_economist()`;
4.  For graphs, `base_size` at least 12 unless the output becomes overly crowded, in which case go down one `base_size`.


**Spreadsheets**  

1.  Whenever counts or other induced results are needed, use formulas unless it's not possible to do so.  This is so that any relevant changes get properly propagated and displayed.




<!--
   Invisible section // Data-norms-2026.09.md
-->
