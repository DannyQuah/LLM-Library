---
fileName: 3AsPlus-sources-v1.1.md
Version: 1.1
Last-edited: 2026.10.18.Sun -- Protocol revision (3AsPlus industrial-policy expansion)
Type: Notes
Tags:
  - 3AsPlus
  - acquiescence
  - adaptation
  - aggregation
  - economicDiplomacy
Created: 2026.10.13.1705.Tue
title: 3AsPlus-sources-v1.1
---

# 3AsPlus: Source inventory — v1.1

This is a starting source inventory for response-first and US-trigger-first research. It is not a list of sources that must all yield qualifying events. Record the *originating* outlet or agency, rather than treating a syndication host as an independent reporter. Verify dates, original text, and document-specific URLs for each accepted observation. The newly added sources below were checked on 14 October 2026 for accessible, dated, readable text; this does not establish comprehensive historical coverage or future uninterrupted access.

### Official / governmental / intergovernmental sources

- **USTR — Office of the United States Trade Representative**
- **White House** — including the Trump White House archive and Obama White House archive
- **USITC — United States International Trade Commission**
- **US Department of State**
- **WTO — World Trade Organization**
- **ASEAN**
- **Australian Government / Department of Foreign Affairs and Trade / Trade Minister**
- **Bank Indonesia**
- **Bank Negara Malaysia**
- **Government of Indonesia / Coordinating Ministry for Economic Affairs**
- **Government of Japan / Prime Minister's Office**
- **Japan METI — Ministry of Economy, Trade and Industry**
- **Korea MOTIE/MOTIR — Ministry of Trade, Industry and Energy / Ministry of Trade, Industry and Resources**
- **Korea.net / Government of the Republic of Korea**
- **Malaysia MITI — Ministry of Investment, Trade and Industry**
- **Monetary Authority / economic authorities of Singapore**, principally **Singapore MTI** and **EDB**
- **Reserve/central-bank and government sources associated with regional local-currency arrangements**
- **Thailand / Bank of Thailand and Thai government sources**
- **Government of India / Press Information Bureau**
- **Philippine Presidential Communications Office**
- **Gulf Cooperation Council Secretariat**

### Additional verified official source families (added in v1.0)

1. **US Department of Commerce — Bureau of Industry and Security (BIS)**. Use for technology export controls, Entity List changes, licensing and semiconductor restrictions, enforcement, and dated rule announcements.
   - [BIS news and press-release archive](https://media.bis.gov/news-updates/all-press-releases)
   - [BIS: advanced-computing semiconductor restrictions and foundry due diligence (15 Jan 2025)](https://www.bis.gov/press-release/commerce-strengthens-restrictions-advanced-computing-semiconductors-enhance-foundry-due-diligence-prevent)
   - [BIS: AI diffusion controls (13 Jan 2025)](https://media.bis.gov/press-release/biden-harris-administration-announces-regulatory-framework-responsible-diffusion-advanced-artificial)
   - **Verification:** The archive and both individual releases exposed dated, substantive readable text. Distinguish BIS's explanatory announcement from the operative rule text.

2. **US Department of the Treasury — Office of Foreign Assets Control (OFAC)**. Use for financial sanctions, designations, general licenses, sanctions guidance, and enforcement.
   - [OFAC recent actions](https://ofac.treasury.gov/recent-actions)
   - [Sanctions List Updates](https://ofac.treasury.gov/recent-actions/sanctions-list-updates)
   - [Regulations and Guidance](https://ofac.treasury.gov/recent-actions/regulations-and-guidance)
   - [Enforcement Actions](https://ofac.treasury.gov/recent-actions/enforcement-actions)
   - **Verification:** Dated action entries and category/year/date search filters exposed readable text. Verify each specific designation, general license, or guidance document separately before coding.

3. **Office of the Federal Register / FederalRegister.gov**. Use for full US rule texts, publication dates, effective dates, statutory authority, amendments, and operative scope, including BIS and Treasury measures.
   - [Federal Register search](https://www.federalregister.gov/)
   - [Investment-security final rule, 89 FR 90398 (15 Nov 2024)](https://www.federalregister.gov/documents/2024/11/15/2024-25422/provisions-pertaining-to-us-investments-in-certain-national-security-technologies-and-products-in)
   - **Verification:** The rule's full text, issuing agency, publication information, and 2 Jan 2025 effective date were accessible. **Legal-status caveat:** FederalRegister.gov's HTML/XML rendering is an unofficial informational rendition; consult the linked official PDF on govinfo.gov where authoritative legal text matters.

4. **US Department of the Treasury — Investment Security**, especially the **Outbound Investment Security Program** and the Office of Investment Security. Use for CFIUS-related material and outbound-industrial policy, prohibitions, notification rules, and enforcement. Treat inbound CFIUS reviews and outbound investment rules as distinct mechanisms.
   - [Outbound Investment Security Program](https://home.treasury.gov/policy-issues/international/outbound-investment-program)
   - [Program Regulations](https://home.treasury.gov/policy-issues/international/outbound-investment-program/program-regulations)
   - [Program FAQs](https://home.treasury.gov/policy-issues/international/outbound-investment-program/frequently-asked-questions)
   - [Program Enforcement](https://home.treasury.gov/policy-issues/international/outbound-investment-program/enforcement)
   - **Verification:** Readable program overview, dated rulemaking chronology, final-rule and effective-date information, FAQs, and enforcement material were available. Not every CFIUS case is publicly disclosed; absence of a record is not evidence of no review.

5. **European Commission — Directorate-General for Trade and Economic Security (DG TRADE)**. Use especially for EU–Asian trade agreements, negotiating rounds, joint statements, and outward Aggregation involving European partners.
   - [European Commission trade and economic security news](https://policy.trade.ec.europa.eu/news_en)
   - **Verification:** The Commission's dated trade-policy news listing was accessible as readable text. Verify specific individual articles and any linked agreement or joint-statement text before treating them as event evidence. EU institutional reports are primary accounts of the EU position, not independent corroboration of Asian governments' motives.

### News organisations

- **Reuters** — by far the most frequently used news-reporting source; often accessed through syndication
- **Yonhap News Agency**
- **ABC News Australia**
- **The Japan Times**
- **Al Jazeera**

### Reuters syndication / republication sites

These should **not** be treated as independent news sources when the underlying story is Reuters:

- **Investing.com**
- **Business Standard**
- **ThePrint**
- **Yahoo Finance**

So for source-diversity purposes count those principally as **Reuters**, not as five separate journalistic sources. Retain both the original outlet and hosting URL when the full original is inaccessible.

### Research/commentary sources consulted around interpretation

These have informed the broader framing but are not generally the sources establishing individual event observations:

- **ISEAS – Yusof Ishak Institute**
- **Foreign Affairs**, particularly Khong and Liow on Southeast Asian alignment/choice

### Operational source-use conventions

- Record `source_outlet` (originator), `source_URL` (document-specific URL), `source_type` (official, independent news, research/commentary, legal text), publication date, and any syndication host separately.
- Prefer the actual dated release, rule, article, or official record over an agency landing page for a coded event. A landing page is a discovery entry point, not itself event evidence.
- Cross-check US official claims against Third-Nation official sources and independent reporting wherever feasible; sources may disagree about concessions and implementation.
- The additional five families strengthen coverage of technology controls, financial sanctions, industrial policy, and non-US coalition-building. They do not replace country-language sources for Asian responses.
- Maintain a search log of inaccessible, paywalled, missing, or undated results; do not convert failed access into a substantive zero.

<!--
   Invisible section // 3AsPlus-sources-v1.1.md
-->

### Additional industrial-policy sources (v1.1)

- **US Treasury / Internal Revenue Service (IRS)** — Inflation Reduction Act clean-vehicle credits, final-assembly, battery, and critical-mineral guidance; consult dated notices, regulations, and individual release text at https://www.irs.gov/credits-deductions/clean-vehicle-credits and https://www.federalregister.gov/ .
- **US Department of Energy (DOE)** — industrial supply-chain grants, loans and location/eligibility conditions: https://www.energy.gov/ .
- **US Department of Commerce / CHIPS Program Office** — CHIPS incentives, guardrails, awards, and restrictions tied to countries of concern: https://www.nist.gov/chips .
- **US Office of Management and Budget / federal procurement sources** — Buy American and procurement preferences, subject to evidence of external geoeconomic purpose: https://www.acquisition.gov/ .
- **Korea MOTIE and Yonhap** — Korean government objections and negotiations concerning IRA electric-vehicle provisions; verify document-level dates and original statements.
- **Japan METI, BIS, and Netherlands government trade authorities** — contemporaneous documents concerning 2023 semiconductor-equipment controls and trilateral understanding; assess both convergence and divergence.

These are research entry points, **not claims that specific source documents were verified in this revision**. The substantive coding still requires dated document-level evidence. Investment Security sources remain relevant as an instrument subset of industrial policy.
