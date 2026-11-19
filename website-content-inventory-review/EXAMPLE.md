# Website content inventory review: an invented example

*Illustrative example with invented data.* Firm K is an invented 80-person accounting and advisory firm. Its marketing lead owns the website and runs this review each quarter; this quarter it also comes before a planned redesign. The pages, addresses, dates and figures below are all invented, and people appear only by role. A real export would run to a few hundred rows; this one is kept to twenty so every figure can be checked by hand.

The inputs come first, in full, so the workflow template can be run on them. The review follows.

## The inputs

### 1. Site rules (typed by the marketing lead)

```
Site: Firm K website
Today: Thursday 19 November 2026
Review is for: marketing lead
Stale limits, days since last update:
  home: 180
  service: 365
  article: 730
  landing: 180
Page types that must have an owner: home, service, landing
Titles: 10 to 60 characters
Descriptions: 50 to 160 characters
Drafts: older than 120 days counts as old
Title suffix: none
```

### 2. The page export from your content management system (pages-2026-11-19.csv, exported Thursday 19 November 2026)

The columns are page ID, address, title, page type, status, author, owner, date published, date last updated, meta description and word count, under the default headers. The export holds no page text.

```
page_id,url,title,page_type,status,author,owner,published_at,last_updated_at,meta_description,word_count
P001,/,Firm K: accounting and advice for growing companies,home,published,Marketing lead,Marketing lead,2022-03-01,2026-06-02,"Bookkeeping, payroll, tax and finance support for companies with ten to two hundred staff.",640
P002,/services/bookkeeping/,Bookkeeping,service,published,Content writer,Head of client services,2022-03-01,2025-09-30,"Monthly bookkeeping with a named accountant, a close calendar and reports you can read.",820
P003,/services/payroll/,Payroll services,service,published,Content writer,,2022-03-01,2026-03-10,"Payroll for teams of five to two hundred, with pay runs checked by a second person.",760
P004,/services/tax-planning/,Tax planning for owner-managed companies and their company directors,service,published,Tax lead,Tax lead,2022-05-16,2025-08-14,"Year-round tax planning for owner-managed companies: what to set aside each quarter, when to pay it, how directors draw income, and which records your accountant needs from you.",1130
P005,/services/fractional-cfo/,Part-time finance director,service,published,Advisory lead,,2023-01-09,2025-11-03,"A part-time finance director for budgets, board packs, lender conversations and pricing.",910
P006,/insights/year-end-checklist/,Year-end checklist for small businesses,article,published,Content writer,,2023-11-20,2023-11-20,"Twelve things to gather before your year end, and who in your team usually holds each one.",1450
P007,/insights/year-end-checklist-2025/,Year End Checklist for Small Businesses,article,published,Content writer,,2025-12-01,2025-12-01,"What to gather before the year end: records, balances, payroll totals and open questions.",1320
P008,/insights/read-a-cash-flow-statement/,How to read a cash flow statement,article,published,Advisory lead,,2025-02-10,2025-02-10,,1680
P009,/insights/cash-flow-forecasting-starter/,Cash flow forecasting: a starter guide,article,published,Advisory lead,,2025-06-23,2025-06-23,"A plain guide to building your first thirteen-week cash flow forecast in a spreadsheet.",2010
P010,/insights/cash-flow-seasonal/,Cash flow forecasting for seasonal businesses,article,published,Advisory lead,,2025-09-08,2025-09-08,"A plain guide to building your first thirteen-week cash flow forecast in a spreadsheet.",1890
P011,/offers/free-tax-review/,Free tax review,landing,published,Marketing lead,Marketing lead,2025-10-06,2026-02-01,Book a free review.,310
P012,/offers/tax-review/,Free tax review!,landing,published,Marketing lead,,2026-09-14,2026-10-01,"Book a free thirty-minute review of last year's tax position with one of our tax team.",290
P013,/events/year-end-webinar-2025/,Year-end planning webinar 2025,event,published,Marketing lead,,2025-10-15,2025-10-15,"Join our tax and advisory leads for an hour on year-end planning for owner-managed firms.",430
P014,/insights/untitled-17/,,article,published,Content writer,,2026-01-20,2026-01-20,,0
P015,/news/,News,article,published,Marketing lead,Marketing lead,2022-03-01,2026-11-02,"The latest announcements, event dates and guides from the Firm K team, newest first.",120
P016,/insights/digital-tax-records/,Digital tax records: what changes,article,draft,Tax lead,,,2026-05-04,,1240
P017,/offers/spring-offer/,Spring offer,landing,draft,Marketing lead,Marketing lead,,2026-09-30,,180
P018,/services/bookkeeping-services/,Bookkeeping services,service,draft,Content writer,Head of client services,,2026-02-15,,700
P019,/insights/old-budget-guide/,Budget guide 2021,article,archived,Advisory lead,,2021-04-12,2023-01-05,"How to build an annual budget.",980
P020,/insights/cash-flow-statement-guide/,How to read a cash flow statement,article,published,Advisory lead,,2026-04-12,2026-03-30,"Operating, investing and financing: what each part of the cash flow statement tells an owner.",1550
```

## The review

WEBSITE CONTENT INVENTORY REVIEW: Firm K website, as of Thursday 19 November 2026

For: marketing lead. Export: pages-2026-11-19.csv, 20 rows. Rules: stale limits home: 180 days, service: 365 days, article: 730 days, landing: 180 days; owner needed for home, service, landing; titles 10 to 60 characters; descriptions 50 to 160 characters; drafts older than 120 days; title suffix none. Defaults used: stale limit for event pages, 365 days.

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
Not tested for an owner (page type not in the owner list): article, event.

3. TITLES: missing 1; too long 1; too short 1; shared 1 group
Missing: P014, /insights/untitled-17/.
Too long: P004, /services/tax-planning/: 68 characters (longest allowed 60).
Too short: P015, /news/: 4 characters (shortest allowed 10).
Shared: "How to read a cash flow statement": P008, P020.

4. DESCRIPTIONS: missing 2; too long 1; too short 1; shared 1 group
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
- P014, /insights/untitled-17/: word_count: 0; a published page with no words recorded.
- P020, /insights/cash-flow-statement-guide/: last_updated_at: 2026-03-30; earlier than published_at 2026-04-12. Stale test not run.

8. QUESTIONS FOR THE MARKETING LEAD
1. Past their stale date: six published pages are over the limit for their page type: P004, P002 and P005 (service), P006 (article), P011 (landing) and P013 (event, default limit). What does the marketing lead decide for each, and who carries it out?
2. No owner: P003, P005 and P012 are page types that need an owner, and none is recorded. Who owns each?
3. Titles: P014 has no title, P004 is over the longest allowed, P015 is under the shortest, and P008 and P020 share one title. Who settles the title of each?
4. Descriptions: P008 and P014 have none, P004 is over the longest allowed, P011 is under the shortest, and P009 and P010 share one description. Who settles the description of each?
5. Old drafts: P016 and P018 have not been updated for more than 120 days. Is each draft still wanted, and who decides?
6. Likely duplicates: P006 and P007, P008 and P020, P011 and P012 have titles that match once case and punctuation are set aside. Is each pair one page or two, and who decides?
7. Records to check: P014 is published with a word count of 0, and P020's last update is recorded as earlier than its publication. What does the system show for each?

Prepared for the marketing lead to review. Built from the page export alone: no page was visited and no page text was read. Nothing has been rewritten, unpublished, redirected or deleted, and no record was changed. The marketing lead decides each page.

## Checking the figures (not part of the review)

- Days since update, counted from Thursday 19 November 2026: P004 2025-08-14, 462; P002 2025-09-30, 415; P005 2025-11-03, 381; P006 2023-11-20, 1,095; P011 2026-02-01, 291; P013 2025-10-15, 400. Days over: 462 − 365 = 97; 415 − 365 = 50; 381 − 365 = 16; 1,095 − 730 = 365; 291 − 180 = 111; 400 − 365 = 35.
- Published pages within their limit: P001 home, 170 days (180); P003 service, 254 (365); P007 article, 353 (730); P008 article, 647 (730); P009 article, 514 (730); P010 article, 437 (730); P012 landing, 49 (180); P014 article, 303 (730); P015 article, 17 (730). P020 is not tested because its last update is earlier than its publication. 6 stale + 9 within + 1 not tested = 16 published.
- Drafts: P016 199 days and P018 277 days, both over 120; P017 50 days, within. 2 + 1 + 0 = 3 drafts.
- Lengths in characters: P004's title 68 and description 177; P015's title 4; P011's description 19. Every other published title is 11 to 51 characters and every other description 83 to 93.
- Published pages with a finding: P002, P004, P005, P006, P011, P013 (section 1); P003, P012 (section 2); P008, P009, P010, P014, P015, P020 (sections 3, 4, 7); P007 (section 6 only). 6 + 2 + 6 + 1 = 15. With none: P001. 15 + 1 = 16.
- Likely duplicates: "Year-end" and "Year End" both become "year end"; "Free tax review!" loses its "!". P002 "Bookkeeping" and P018 "Bookkeeping services" do not match and are not grouped. P019 is archived and is not compared.
- Rows: 16 published + 3 draft + 1 archived = 20.
