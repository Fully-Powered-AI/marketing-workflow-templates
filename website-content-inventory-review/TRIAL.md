# Website content inventory review: trial on its example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-19

The inputs were the example "Firm K" in `public/example.md`: the site rules and the 20-row page export under "The inputs". No client data was used. I did not write the template; I ran it once as written.

## Inputs used

- The site rules and the page export (pages-2026-11-19.csv) in `public/example.md`, section "The inputs", unchanged.
- The template's instruction block and output format in `member/template.md`.

## What came out

The full review, run from the instruction block and the output format. Nothing in the template made it stop: every header matched, no page ID repeated, every status was one of the three, every date was readable and unambiguous, and no column held page text. I used a short script for the date subtraction and character counts and checked the results against the template's rules.

```
WEBSITE CONTENT INVENTORY REVIEW: Firm K website, as of Thursday 19 November 2026
For: marketing lead. Export: pages-2026-11-19.csv, 20 rows. Rules: stale limits home 180 days, service 365 days, article 730 days, landing 180 days; owner needed for home, service, landing; titles 10 to 60 characters; descriptions 50 to 160 characters; drafts older than 120 days; title suffix none. Defaults used: stale limit for event pages, 365 days.
COUNT
Pages read: 20 (rows in the export: 20). Published 16, draft 3, archived 1 (archived pages are counted, not checked).
Published pages with at least one finding: 15. With none: 1 (P001).
Drafts older than the limit: 2. Within the limit: 1 (P017). With a date to check: 0.
1. PAST THEIR STALE DATE, BY PAGE TYPE: 6
Service (limit 365 days)
- P004, /services/tax-planning/: last updated 2025-08-14, 462 days ago, 97 days over. Owner: Tax lead.
- P002, /services/bookkeeping/: last updated 2025-09-30, 415 days ago, 50 days over. Owner: Head of client services.
- P005, /services/fractional-cfo/: last updated 2025-11-03, 381 days ago, 16 days over. Owner: not recorded.
Article (limit 730 days)
- P006, /insights/year-end-checklist/: last updated 2023-11-20, 1,095 days ago, 365 days over. Owner: not recorded.
Landing (limit 180 days)
- P011, /offers/free-tax-review/: last updated 2026-02-01, 291 days ago, 111 days over. Owner: Marketing lead.
Event (limit 365 days, default)
- P013, /events/year-end-webinar-2025/: last updated 2025-10-15, 400 days ago, 35 days over. Owner: not recorded.
Page types with no stale page: home.
2. PUBLISHED PAGES WITH NO OWNER: 3
- P003, /services/payroll/, service. Author: Content writer.
- P005, /services/fractional-cfo/, service. Author: Advisory lead.
- P012, /offers/tax-review/, landing. Author: Marketing lead.
3. TITLES: missing 1; too long 1; too short 1; shared 1 groups
Missing: P014, /insights/untitled-17/.
Too long: P004, /services/tax-planning/: 68 characters (longest allowed 60).
Too short: P015, /news/: 4 characters (shortest allowed 10).
Shared: "How to read a cash flow statement": P008, P020.
4. DESCRIPTIONS: missing 2; too long 1; too short 1; shared 1 groups
Missing: P008, /insights/read-a-cash-flow-statement/; P014, /insights/untitled-17/.
Too long: P004, /services/tax-planning/: 177 characters (longest allowed 160).
Too short: P011, /offers/free-tax-review/: 19 characters (shortest allowed 50).
Shared: "A plain guide to building your first thirteen-week cash flow forecast in a spreadsheet.": P009, P010.
5. DRAFTS OLDER THAN THE LIMIT: 2
- P016, /insights/digital-tax-records/, article: last updated 2026-05-04, 199 days ago (limit 120). Author: Tax lead. Owner: not recorded.
- P018, /services/bookkeeping-services/, service: last updated 2026-02-15, 277 days ago (limit 120). Author: Content writer. Owner: Head of client services.
6. LIKELY DUPLICATES BY TITLE: 3 groups
- P006 (published), P007 (published): "Year-end checklist for small businesses" / "Year End Checklist for Small Businesses".
- P008 (published), P020 (published): "How to read a cash flow statement" / "How to read a cash flow statement". (also under section 3, shared titles)
- P011 (published), P012 (published): "Free tax review" / "Free tax review!".
7. RECORDS TO CHECK: 2
- P014, /insights/untitled-17/: word_count: 0; a published page with a word count of 0.
- P020, /insights/cash-flow-statement-guide/: last_updated_at: 2026-03-30, published_at: 2026-04-12; the last update is earlier than the publication date. Stale test not run.
8. QUESTIONS FOR THE MARKETING LEAD
1. Past their stale date: six published pages are past the limit for their type (P004, P002, P005, P006, P011, P013). Who decides what happens to each page, and who owns it?
2. Published pages with no owner: P003, P005 and P012 are service or landing pages with no owner recorded. Who owns each?
3. Titles: P014 has no title, P004 is 68 characters, P015 is 4 characters, and P008 and P020 share one title. Who decides what each title should be?
4. Descriptions: P008 and P014 have none, P004 is 177 characters, P011 is 19 characters, and P009 and P010 share one description. Who decides what each should be?
5. Drafts older than the limit: P016 (199 days) and P018 (277 days) have not been updated for longer than 120 days. Who decides whether each is still wanted?
6. Likely duplicates by title: P006 and P007, P008 and P020, and P011 and P012 have titles that match once case and punctuation are ignored. Who decides whether each pair is the same page?
7. Records to check: P014 records a word count of 0, and P020 records a last update earlier than its publication date. What do the records in the content management system show for each?
Prepared for the marketing lead to review. Built from the page export alone: no page was visited and no page text was read. Nothing has been rewritten, unpublished, redirected or deleted, and no record was changed. The marketing lead decides each page.
```

## What was observed

- **Every required part was produced:** the heading, the rules line, the count, sections 1 to 7, the questions and the closing line. All counts added up (20 rows = 16 published + 3 draft + 1 archived; 15 published pages with a finding + 1 without = 16; 2 old drafts + 1 within + 0 to check = 3).
- **Contamination, stated plainly:** while reading the example file for its inputs I also saw its count block and section 1 (the stale pages). The rest of my output was worked out from the inputs alone. The stale section is therefore not an independent result.
- **Difference from the published example:** the figures, page IDs, groupings and order matched in every section. The wording differed in these places only: (1) the example prints "shared 1 group" where the format says "[n] groups" and I printed "1 groups"; (2) in the rules line the example writes "home: 180 days" and I wrote "home 180 days" (the format shows a colon after the page type; mine departed from it); (3) section 7 names the field "word count" in the example and `word_count` in mine; (4) the questions use different words for the same facts.
- **Anything not in the inputs:** nothing in either review. Every figure and page ID traces to the export or the rules.
- **Where the instructions left room to guess:**
  - Two blank descriptions (P008, P014) or two blank titles are not a "shared" group. The template does not say so; I treated blank as missing only.
  - The procedure's step numbers, the instruction block's step numbers and the output's section numbers all differ (for example, procedure step 6 produces output section 3), and step 10 refers to output section numbers. It is easy to misread.
  - The format's "[n] groups" has no singular form.
  - "Stale test not run" is defined for date problems only. P014's word count of 0 is not a date problem, so P014 was still tested for staleness (303 days, within 730). I read it that way.
  - Section 8 asks for "the facts and the page IDs and who decides or what the record shows" but gives no example question, so the wording is my own.
  - The input rules have no place for the export's file name; I took it from the example's heading.
  - A page type with no rule that is not in the owner list (event) is neither tested for an owner nor listed anywhere. That is what the rules say, but it is worth a sentence.
- **Limits of this trial:** one run, one sample export of 20 rows, one model. It does not show how the template behaves on a real export of hundreds of pages, on a stop condition (none was triggered here), or in other products.

## After this run

Edits made to the template after this run, by its editorial review, have not been run again: a singular for "1 group", a rule that blank titles and descriptions are missing and never shared, removing the title suffix in the duplicate test, section numbers on the procedure steps, column headers as the field names in section 7, a line naming page types not tested for an owner (printed under section 2), and a place for the export's file name. The record above is unchanged from the run. Also edited after the run, without a re-run: the instruction block now lists a missing or empty export among the stops and the website owner among the defaults, two over-long lines in it were re-wrapped, and a rule says a draft whose only note is a shared url is still tested for age, and that a duplicate group holding a draft is not marked as a shared-title group. None of these touches the example's inputs or output.
