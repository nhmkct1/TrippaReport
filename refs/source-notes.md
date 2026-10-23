# Local review revision: sources and decisions

## Status and scope

This revision was prepared locally for review and is now approved by the user for commit and push. Confluence and application repositories have not been modified or used as implementation evidence. The previous published revision remains available in Git history.

The report now contains exactly three numbered chapters:

1. Introduction.
2. Functional and Non-Functional Requirements.
3. Architecture Design.

The existing-system analysis and the old stakeholders, scope tables, business-rule section, prioritization and traceability exposition are excluded. The FR/NFR requirements themselves remain intact, including references to administration, mobile interaction and unresolved policies.

## Confluence provenance

| Use | Source | Version | Source update (UTC) |
| --- | --- | --- | --- |
| Introduction | [Chapter 1, page 14647353](https://trip-planner-hcmut.atlassian.net/wiki/spaces/TPD/pages/14647353) | 2 | 2026-10-08 14:51:54 |
| FR/NFR content | [Chapter 3, page 12025880](https://trip-planner-hcmut.atlassian.net/wiki/spaces/TPD/pages/12025880) | 6 | 2026-10-08 14:35:35 |
| Design starting point | [Chapter 4, page 15564818](https://trip-planner-hcmut.atlassian.net/wiki/spaces/TPD/pages/15564818) | 1 | 2026-10-08 14:35:14 |

The first two sources were retrieved through Atlassian on 23 October 2026 and preserved during the earlier conversion. The design page was read directly for this revision; it contained only a checklist for architecture, database and UI design, not a developed architecture. Architecture Design is therefore newly authored analysis rather than converted source prose. No source page was changed.

Requirements coverage: 21 requirement tables, comprising all 111 distinct FR identifiers and 62 distinct NFR identifiers. FR-11 was moved into the Functional Requirements section, ahead of the NFRs. The wording of every requirement and its existing acceptance criterion is retained. All 13 Chapter 3 TBD occurrences remain. Old table labels were renamed for the new chapter, without changing requirement identifiers. The source checklist is also retained as five explicit TBD subsections under System Models: Use Case Table, Use Case Diagram, Activity Diagram, Sequence Diagram and Class Diagram. These are pending models; the two completed architecture diagrams remain in Chapter 3. The 13 TBD occurrences within requirements are unchanged; the five new model placeholders are additional.

## Proposed architectural decision

- Compare a conventional layered monolith, modular monolith, two-service candidate and microservices.
- Select **modular monolith with layered business modules**, one backend deployment unit and one application database.
- Define six logical modules: Accounts and Preferences, Trip Management, Planning and Feasibility, Place and Route Integration, AI Assistance, and Administration.
- Keep authoritative trip writes in Trip Management and shared feasibility policies in Planning and Feasibility. AI supplies typed suggestions through the ordinary validated workflow.
- Use presentation/API, application, domain and infrastructure layers where useful; maintain inward source dependencies and public module contracts.
- Make external providers replaceable through adapters. No language, framework, cloud platform, independent AI runtime, service broker or deployment cluster is mandated.
- Weighted scores are transparent engineering judgments for this project, not measured data. The chosen weights favor delivery, modularity and trip consistency. Sensitivity to an increased scaling weight is also shown.
- Transaction/versioning, duplicate protection, timeout handling and verification scenarios are proposed design mechanisms. They do not assert that business policies are approved or the implementation already exists.

## Architecture references

The five primary sources are linked and cited inside Chapter 3: Microsoft common web architectures; Richards and Ford's service-based architecture chapter (publisher preview); Microsoft microservices architecture; Fowler's Monolith First; and Robert C. Martin's The Clean Architecture. Sources support architectural concepts; Trippa's boundaries, matrix scores and decision are the newly proposed project analysis. References were checked on 23 October 2026.

## Pending user review

1. Review the proposed modular-monolith choice and its module responsibilities before implementation alignment.
2. Approve business policy details and quantitative NFR targets that remain TBD; this revision intentionally does not decide them.
3. Complete the program, examination committee, supervisor, committee secretary, student names/IDs and defense month/year. The cover template and university logo have now been supplied and integrated.

## Prose-shortening revision

At the user's request, narrative prose was shortened by approximately 20% (3,633 to 2,912 words using the same count that excludes tables, headings, captions and bibliography entries). Introduction was shortened by 22.1% and Architecture Design by 20.2%; requirement introductions were also condensed. All requirement tables, architecture tables, requirement IDs, references, diagrams and five system-model TBD placeholders are unchanged. The architectural selection and its technical safeguards remain intact. The user subsequently approved committing and pushing this revision.

## Cover revision

The cover is adapted from the user-supplied LaTeX title page, preserving its double frame, university/faculty heading, logo, project title and right-side committee/student block. The supplied `01_logobachkhoasang.png` is copied unchanged to `images/hcmut.png`. Cover text is in English, using Specialized Project and the Trippa title. Institution names were checked against [HCMUT](https://hcmut.edu.vn/en) and the [Faculty of Computer Science and Engineering](https://cse.hcmut.edu.vn/en/bo-mon-he-thong-va-mang-may-tinh). All unknown fields remain TBD, including the defense date. The three student slots follow the source template and can be adjusted when the actual team list is provided. Cover data is centralized in `metadata.tex`; layout is isolated in `frontmatter/cover.tex`. The report body is unchanged. The updated local PDF is `output/pdf/trippa-report-review-cover.pdf`; the user subsequently approved publishing this revision to GitHub.
