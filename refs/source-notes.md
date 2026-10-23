# Source notes and pending decisions

## Scope and provenance

Retrieved on 23 October 2026 from the existing Atlassian connection. Only the following published pages were used; no application source code or other Confluence sections were used. Confluence was not modified.

| Chapter | Confluence page | Version | Last updated (UTC) |
| --- | --- | --- | --- |
| 1. Introduction | [14647353](https://trip-planner-hcmut.atlassian.net/wiki/spaces/TPD/pages/14647353) | 2 | 2026-10-08 14:51:54 |
| 2. Existing System Analysis | [12025865](https://trip-planner-hcmut.atlassian.net/wiki/spaces/TPD/pages/12025865) | 9 | 2026-10-08 14:38:04 |
| 3. System Analysis | [12025880](https://trip-planner-hcmut.atlassian.net/wiki/spaces/TPD/pages/12025880) | 6 | 2026-10-08 14:35:35 |

Source inventory: Chapter 2 contains one comparison table with 12 data rows; Chapter 3 contains 25 tables with 217 data rows. All table cells are preserved. Chapter 1 contains no tables. The source pages contain no embedded images or hyperlinks to recover as bibliography entries.

Requirement coverage: all 111 distinct functional requirement IDs and 62 distinct non-functional requirement IDs are retained (173 total). All 13 Chapter 3 occurrences of TBD are retained.

## Editorial decisions

- Removed the leading Vietnamese weekly work notes and unfinished modeling checklist from Chapters 2 and 3. They are internal planning notes, not report prose.
- Used the requested chapter titles and automatic section numbering. In particular, the source Chapter 3 heading "Chapter 2. Requirements Analysis" and its `2.x` prefixes were corrected to Chapter 3 / `3.x`.
- Corrected the opening Chapter 3 reference to the existing-system comparison to point to Chapter 2, where that comparison actually appears.
- Preserved the distinction between ten functional areas in Section 3.4 and the additional FR-11 mobile requirements in Section 3.6.
- Kept functional/non-functional identifiers, table contents, requirement intentions, TBD thresholds, and tentative administration scope.
- Replaced two occurrences of the incomplete `TPD-export(2)` reference and four occurrences of `ShortTrip_Planner_Architecture_…` with visible **[source TBD]** markers. Their intended bibliographic targets have not been guessed. A source note explains this in Chapter 2.
- No bibliography, diagrams, test results, implementation claims, or numerical acceptance criteria have been invented.
- The cover is provisional. Institution, authors, and supervisor remain TBD in `metadata.tex`.

## Questions for the next revision

1. What are the approved business rules for budget enforcement, unknown prices/opening hours, required-place inclusion, trip-state transitions, guest retention, and replanning confirmation?
2. What numerical NFR targets should replace TBD (latency, concurrency/capacity, availability, usability, device testing, and AI data retention)?
3. What administration capabilities are required in this project version?
4. Which use-case tables and UML diagrams should be included, and will approved source diagrams be provided or should they be drafted for review?
5. What are the exact sources behind `TPD-export(2)` and `ShortTrip_Planner_Architecture_…`? What citation style is required, and may official product sources be researched for the Chapter 2 comparison?
6. Please provide the official cover, institution/faculty, course/project title, supervisor, team members/student IDs, and submission date.
