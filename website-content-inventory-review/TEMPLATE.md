# Website content inventory review

Workflow template, version 0.1.0.

## Purpose

Read the page export of a website's content management system and return one review for the website owner: published pages past the stale limit for their page type, published pages with no owner where the site requires one, titles and meta descriptions that are missing, outside the site's length limits or shared by two or more pages, drafts older than the site's limit, groups of pages whose titles show they are probably the same page, and records whose dates or word count need checking. Every finding names its page ID and address. A count proves every row was read. The review ends with one question per kind of finding. The assistant works from the export only: it never visits a page, never reads page text, gives no ranking or traffic advice, promises no search result, and rewrites, unpublishes, redirects, archives or deletes nothing. The website owner decides each page.

## When to use it and when not to

Use it once a quarter, and before a redesign or a move to a new content management system, on a fresh export of every page the system holds. It suits any site where the system can list its pages with their type, status, owner and dates, typically a few dozen to a few thousand pages.

Do not use it:

- to judge whether a page's text is accurate, current or well written. The review reads dates and fields, not text; the page owner reads the page;
- to decide what a page should rank for, which keywords to use or how much traffic a page earns. It gives no search or traffic advice and promises no result;
- to write new titles, descriptions or page text, or to plan redirects;
- to crawl the live site or check broken links. It reads the export and nothing else;
- when the export is older than the last round of changes: the review would report work already done.

## Roles

- **Runs it and supplies the export and the rules:** the marketing lead, the website owner, or a content manager or marketing coordinator on their behalf.
- **Reads the review and decides what happens to each page, and who does it:** the website owner.
- **Updates, retitles, unpublishes, redirects or deletes a page:** the page's owner, or whoever the website owner names, in the content management system. Never the assistant.

## Inputs

1. **The page export from your content management system,** one row per page, with these default column headers: `page_id`, `url`, `title`, `page_type`, `status`, `author`, `owner`, `published_at`, `last_updated_at`, `meta_description`, `word_count`. `status` holds exactly one of `published`, `draft` or `archived`. Dates are written as YYYY-MM-DD. `word_count` is a whole number. A blank cell means nothing is recorded. If the export is missing or has no rows, stop and ask.
2. **The site's rules:**
   - the stale limit for each page type, in days since the last update;
   - the page types that must have an owner;
   - the shortest and longest title, in characters;
   - the shortest and longest meta description, in characters;
   - the draft limit, in days since a draft was last updated;
   - a title suffix the site adds to every title and that should be ignored when comparing titles (for example " | Site name"), if any;
   - who the review is for, and the site's name.
   Defaults, used only where a rule is missing: a stale limit of 365 days for any page type without one; every page type needs an owner; titles 10 to 60 characters; descriptions 50 to 160 characters; a draft limit of 90 days; no title suffix; the review is for the website owner. These defaults are house-style starting points for the length and age checks, not search advice. Say which defaults were used; a rule given that happens to equal a default counts as given.
3. **Today's date, and the export's file name or date.** If today's date is not given, stop and ask. Never take it from the export's file name. The file name (or, if none is given, the date of the export) goes in the header line; if neither is given, print "not given".

**Column headers.** If a header in the export does not match the defaults (missing, renamed or extra), stop and ask which column holds what. Never guess a column.

**Page text.** If a column appears to hold the text of the pages rather than the fields above, stop, do not read or repeat it, and ask for the export without it.

The assistant works from the files and notes supplied. It needs no connection to the content management system and never asks for a password or a login code.

## The procedure

1. **Check the inputs.** Confirm every header. Count the rows, not counting the header. If two rows share a `page_id`, stop and ask. If a `status` is anything other than `published`, `draft` or `archived` (such as "scheduled" or "private"), stop and ask how to read it. If a date could be read two ways (03/04/2026), stop and ask which format the export uses.
2. **Set aside archived pages.** Count them by status and check nothing else about them (heading count).
3. **Records to check (section 7).** For each published page, note: `published_at` blank or unreadable; `last_updated_at` blank or unreadable; `last_updated_at` earlier than `published_at`; any date later than today; `word_count` blank, not a whole number, or 0; a `url` that another non-archived row also uses. For each draft, note: `last_updated_at` blank, unreadable or later than today; a `url` that another non-archived row also uses. A blank `published_at` on a draft is normal and is not noted.
4. **Stale pages (section 1).** For each published page whose `last_updated_at` is readable, not later than today and not earlier than `published_at`: days since update = today minus `last_updated_at`, in calendar days. The page is stale when that number is greater than the limit for its page type. Days over = days since update minus the limit. A page with a date noted in step 3 is not tested; say so on its line in section 7.
5. **Owners (section 2).** A published page whose page type must have an owner and whose `owner` is blank has no owner. The author is never treated as the owner. A page type that is not in the owner list is not tested for an owner, whether or not it has a stale rule; list each such page type that has published pages under section 2.
6. **Titles (section 3),** for published pages, after trimming spaces at both ends and removing the title suffix if one is set. Missing: blank. Too long: more characters than the longest allowed. Too short: fewer than the shortest allowed. Shared: two or more published pages whose titles are identical when case is ignored; list each group once. Blanks count as missing, never as shared.
7. **Meta descriptions (section 4),** for published pages, tested the same way against the description limits, with the same rule that blanks count as missing, never as shared. A description is never compared with its page's title.
8. **Old drafts (section 5).** For each draft whose `last_updated_at` passed step 3: days since update = today minus `last_updated_at`. The draft is old when that number is greater than the draft limit. A draft whose only step-3 note is a shared `url` has a readable date: it is still tested here and counted as old or within the limit, not as a date to check.
9. **Likely duplicates by title (section 6),** across published and draft pages that have a title. Make a comparison form of each title: remove the title suffix if set; lower case; replace "&" with "and"; replace every run of characters that are not letters or digits with one space; trim. Pages whose comparison forms are identical form a group. List each group of two or more once, with each page's status and its title as recorded. Where every page in a group is published and the group also forms a shared-title group in step 6, mark it "(also under section 3, shared titles)". A group that includes a draft is never marked, because section 3 covers published pages only. Use no other test: no synonyms, no word stems and no reading of the page.
10. **Prove the count.** Pages read = rows = published + draft + archived. A published page has a finding when it appears in section 1, 2, 3, 4, 6 or 7. Published pages with at least one finding + published pages with none = published, and the pages with none are listed by ID. Drafts older than the limit + drafts within the limit + drafts with a date to check = drafts. Each section's heading count equals the finding lines under it (the "Not tested for an owner" line is a note, not a finding). If any count does not add up, stop and report the figures; print nothing else.
11. **Write the questions (section 8),** one for each numbered section that has at least one line, in section order, addressed to the person the review is for. Each states the facts and the page IDs and asks who decides or what the record shows. A question never proposes new wording, a redirect, an unpublish, a deletion or a merge, and never says a page should rank or will bring traffic.
12. **Return the review** in the output format to the person who started the run. Do not send it onward.

## Exceptions and stop conditions

- **The export is missing or empty; a header is missing, renamed or extra; two rows share a page ID; a status is not one of the three; a date is ambiguous; today's date is missing:** stop and ask.
- **A column appears to hold page text:** stop; do not read or repeat it; ask for the export without it.
- **The counts in step 10 do not add up:** stop and report the figures.
- **Asked to visit, crawl or fetch a page or the live site:** decline; the review reads the export only.
- **Asked to write a title, a description or page text, or to say which page should be kept:** decline; record the question for the website owner.
- **Asked about rankings, keywords, traffic or what a change will do in search:** decline; the review gives no search advice and promises no result.
- **Asked to unpublish, redirect, archive, delete, assign an owner or change any record:** decline; the website owner decides and the page owner acts in the system.

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

A count of one reads "1 group" ("shared 1 group", "1 group"), never "1 groups". In section 7 name each field by its column header exactly as in the export (`word_count`, `last_updated_at`), never by a plain-language name. The line "Not tested for an owner" is printed under section 2 even when the section reads "None."; it names the page types of published pages that the owner list leaves out, so the reader can see that no owner test was run on them.

Order within sections: section 1 by page type in the order the rules list them, page types with no rule after them in alphabetical order, and within a page type the oldest update first; sections 2, 5 and 7 by page ID; within the lists of sections 3 and 4, by page ID, and shared groups by their first page ID; section 6 by the first page ID of each group. Numbers of a thousand or more take a comma. One day reads "1 day". A page with two problems in section 7 has one line naming both.

When a numbered section is empty, print "None." after its heading. A sub-list in section 3 or 4 with nothing in it reads "None." Never leave a section out. If no section has a line, section 8 reads "None."

## Reviewer checklist

1. The headers matched the defaults, or the mapping was confirmed. (Website owner)
2. Pages read equals the rows in the export, and published, draft and archived add up to it. (Website owner)
3. Published pages with and without a finding add up to the published count, and the pages with none are listed. (Website owner)
4. Every days-since-update figure is today minus the recorded date, and every stale page is over the limit for its own page type. (Content manager)
5. Every title and description length is counted in characters as recorded. (Content manager)
6. No question proposes wording, a redirect, an unpublish, a deletion or a merge, and nothing mentions rankings or traffic. (Website owner)
7. No page text appears anywhere in the review. (Website owner)

## Acceptance tests

Proposed tests. None has been run.

1. **Clean page.** A published service page updated 170 days ago with a 180-day limit, an owner, and title and description within limits. Expected: listed under "With none" in the count, and nowhere else.
2. **One day over.** Limit 365 days, last updated 366 days before today. Expected: stale, "366 days ago, 1 day over".
3. **Exactly at the limit.** Limit 180 days, last updated 180 days before today. Expected: not stale.
4. **Page type with no rule.** An event page with no stale limit given. Expected: tested at 365 days, shown "(limit 365 days, default)", and listed under Defaults used.
5. **Updated before published.** Published 2026-04-12, last updated 2026-03-30. Expected: section 7, "Stale test not run".
6. **Author but no owner.** Owner blank, author recorded, page type needs an owner. Expected: section 2, with the author shown and not treated as owner.
7. **Shared title that differs in case.** "Free tax review" and "FREE TAX REVIEW". Expected: one shared group in section 3 and one group in section 6 marked "also under section 3".
8. **Punctuation only.** "Year-end checklist" and "Year End Checklist". Expected: a likely-duplicate group in section 6, not a shared title.
9. **Old draft.** Draft limit 120 days, draft last updated 199 days ago. Expected: section 5, "199 days ago (limit 120)".
10. **Unknown status.** A row with status "scheduled". Expected: stops and asks how to read it.
11. **Renamed header.** `modified` in place of `last_updated_at`. Expected: stops and asks.
12. **Page text in the export.** A `body` column. Expected: stops, does not repeat it, asks for the export without it.
13. **Asked to rewrite titles and set up redirects.** Expected: declines; the questions record who decides.

## Instructions for the AI assistant

```
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
```

## What to customize

- Your export's headers, or the mapping from them to the defaults.
- [your stale limits], one for each page type you use.
- The page types that must have a named owner.
- [your title limits] and [your description limits], from your house style.
- [your draft limit], and the title suffix your system adds, if any.
- How your system writes statuses, if it uses more than published, draft and archived.
- Who reads the review and who settles each kind of finding.
- Which exports the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 19 November 2026. Written by FullyPowered AI as original work. Editorially reviewed. Tried on its invented example in one run (public/trial.md); the edits made after that run have not been run again. Not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
