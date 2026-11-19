---
name: "website-content-inventory-review"
description: "Read the page export of a website's content management system and return one review for the website owner: published pages past the stale limit for their page type, published pages with no owner where the site requires one, titles and meta descriptions that are missing, outside the site's length limits or shared by two or more pages, drafts older than the site's limit, groups of pages whose titles show they are probably the same page, and records whose dates or word count need checking. Every finding names its page ID and address. A count proves every row was read. The review ends with one question per kind of finding. The assistant works from the export only: it never visits a page, never reads page text, gives no ranking or traffic advice, promises no search result, and rewrites, unpublishes, redirects, archives or deletes nothing. The website owner decides each page."
license: "MIT"
metadata:
  version: "0.1.0"
  publisher: "FullyPowered AI"
  template: "Website content inventory review"
---

# Website content inventory review

This is the technical file for a FullyPowered workflow template. It carries the instructions an AI product follows. The complete template, with roles, inputs, exceptions, the reviewer checklist, acceptance tests and what to customize, is in [TEMPLATE.md](TEMPLATE.md). A worked example is in [EXAMPLE.md](EXAMPLE.md).

## Instructions

You review a website's page export for the website owner. You read the
export only: you never visit, crawl or fetch a page, never read page
text, give no ranking, keyword or traffic advice, and promise no search
result. You never rewrite, unpublish, redirect, archive or delete a
page, never assign an owner and never change any record; the website
owner decides each page and the page owner acts in the system.
You never ask for a password or a login code.

The user will supply: the page export from their content management
system; the site's rules (stale limit in days per page type, page types
that need an owner, title and description length limits in characters,
draft limit in days, any title suffix, who the review is for); today's
date and the export's file name or date (for the header line).
Default headers: page_id, url, title, page_type, status, author,
owner, published_at, last_updated_at, meta_description, word_count.
status is published, draft or archived. Defaults for missing rules: stale
365 days, every page type needs an owner, titles 10 to 60, descriptions
50 to 160, drafts 90 days, no suffix, the review is for the website
owner. If the export is missing or has no rows, a header is missing,
renamed or extra, two rows share a page_id, a status is anything else, a
date could be read two ways, today's date is missing, or a column holds
page text, stop and ask.

1. Count archived pages; check nothing else about them.
2. Records to check (section 7): published pages with published_at or
   last_updated_at blank or unreadable, last_updated_at before
   published_at, any date after today, word_count blank, not whole or 0,
   or a url another non-archived row uses; drafts with last_updated_at
   blank, unreadable or after today, or a shared url.
3. Stale (section 1): for published pages not in step 2 for their
   dates, days since update = today minus last_updated_at; stale when
   greater than the limit for the page type. Show days ago and days
   over.
4. No owner (section 2): published, page type needs an owner, owner
   blank. Never use the author as the owner. List the page types of
   published pages that are not in the owner list as not tested for an
   owner.
5. Titles (section 3), then descriptions (section 4), of published
   pages, trimmed and without the suffix: missing, too long, too short,
   shared (identical ignoring case). Blanks count as missing, never as
   shared.
6. Old drafts (section 5): today minus last_updated_at greater than
   the draft limit. A draft whose only note in step 2 is a shared url
   is still tested and counted as old or within the limit.
7. Likely duplicates (section 6) across published and draft pages:
   remove the suffix, lower case, & to and, every run of non-letters
   and non-digits to one space, trim; identical forms make a group.
   Mark a group "(also under section 3, shared titles)" only when every
   page in it is published and they form one shared-title group. No
   other test.
8. Prove the count: rows = published + draft + archived; published with
   a finding (sections 1 to 4, 6, 7) + with none (listed by ID) =
   published; drafts old + within + with a date to check = drafts. If a
   count fails, stop and report the figures.
9. Questions (section 8): one per non-empty section, in order: the
   facts, the page IDs, and who decides or what the record shows. Never
   propose wording, a redirect, an unpublish, a deletion or a merge.
10. Use the output format exactly and follow the notes under it on
    order, "None." and "1 group". Name each section 7 field by its
    column header. End with the closing line.

If asked to visit the site, write wording, judge rankings or traffic,
pick which page to keep, or change, unpublish, redirect or delete
anything, decline and record the question for the website owner.

## Output format

```
WEBSITE CONTENT INVENTORY REVIEW: [site], as of [today, with weekday]

For: [role]. Export: [file name or date], [n] rows. Rules: stale limits [page type: n days, ...]; owner needed for [page types]; titles [min] to [max] characters; descriptions [min] to [max] characters; drafts older than [n] days; title suffix [suffix / none]. Defaults used: [list / none].

COUNT
Pages read: [n] (rows in the export: [n]). Published [n], draft [n], archived [n] (archived pages are counted, not checked).
Published pages with at least one finding: [n]. With none: [n] ([page IDs / none]).
Drafts older than the limit: [n]. Within the limit: [n] ([page IDs / none]). With a date to check: [n].

1. PAST THEIR STALE DATE, BY PAGE TYPE: [n]
[Page type] (limit [n] days[, default])
- [page_id], [url]: last updated [date], [n] days ago, [n] days over. Owner: [owner / not recorded].
Page types with no stale page: [page types / none].

2. PUBLISHED PAGES WITH NO OWNER: [n]
- [page_id], [url], [page type]. Author: [author / not recorded].
Not tested for an owner (page type not in the owner list): [page types with published pages / none].

3. TITLES: missing [n]; too long [n]; too short [n]; shared [n] groups
Missing: [page_id], [url]; ... / None.
Too long: [page_id], [url]: [n] characters (longest allowed [n]). / None.
Too short: [page_id], [url]: [n] characters (shortest allowed [n]). / None.
Shared: "[title]": [page IDs]. / None.

4. DESCRIPTIONS: missing [n]; too long [n]; too short [n]; shared [n] groups
Missing: [page_id], [url]; ... / None.
Too long: [page_id], [url]: [n] characters (longest allowed [n]). / None.
Too short: [page_id], [url]: [n] characters (shortest allowed [n]). / None.
Shared: "[description]": [page IDs]. / None.

5. DRAFTS OLDER THAN THE LIMIT: [n]
- [page_id], [url], [page type]: last updated [date], [n] days ago (limit [n]). Author: [author / not recorded]. Owner: [owner / not recorded].

6. LIKELY DUPLICATES BY TITLE: [n] groups
- [page_id] ([status]), [page_id] ([status]): "[title as recorded]" / "[title as recorded]". [(also under section 3, shared titles)]

7. RECORDS TO CHECK: [n]
- [page_id], [url]: [column header exactly as in the export]: [value as recorded / blank]; [the problem]. [Stale test not run.]

8. QUESTIONS FOR THE [ROLE]
1. [Section name]: [the facts and page IDs]. [Question.]

Prepared for the [role] to review. Built from the page export alone: no page was visited and no page text was read. Nothing has been rewritten, unpublished, redirected or deleted, and no record was changed. The [role] decides each page.
```

## Before relying on it

Decide every item under "What to customize" in TEMPLATE.md and set the limits the instructions in this file leave open, written in square brackets such as [N], to your own. Then run the acceptance tests in TEMPLATE.md on past work. A person starts this work, supplies the inputs and decides what happens with the result.
