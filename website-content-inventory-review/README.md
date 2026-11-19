# Website content inventory review

A quarterly review from your page export: stale pages by type, pages with no owner, title and description gaps, old drafts and likely duplicate pages.

> [!TIP]
> **Missing a template that is not listed here, or want these customized for your organization? Reach out to us.** This is a template, made to be customized and deployed. FullyPowered AI customizes and builds AI workflows, connects them to your business systems, installs them in your agents and puts them in the hands of the people who own the work. [See Website content inventory review on our website](https://fullypowered.ai/workflows/website-content-inventory-review/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-website-content-inventory-review&from=gh-website-content-inventory-review). Not sure where to start? Email hello@fullypowered.ai and a person will answer.

**Quick start**

1. Read EXAMPLE.md to see what a good result looks like.
2. Copy all of TEMPLATE.md into your assistant, then give it your own inputs, or the sample ones from EXAMPLE.md.
3. Read what comes back. It marks what it checked and what is left for you.

*Workflow template · Marketing and content · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/website-content-inventory-review/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-website-content-inventory-review&from=gh-website-content-inventory-review)*

## The outcome

A site with a few hundred pages stops being a guess. The marketing lead or website owner sees, on one review, every published page that has gone longer without an update than your own rules allow for its type, every page that should have an owner and has none, every title and description that is missing, outside your length limits or shared with another page, every draft that has sat too long, and the pages whose titles say they are probably the same page twice.

Each finding names the page ID and the address, so nobody has to hunt. A count at the top ties every number back to the export: pages read, pages by status, and published pages with and without a finding. A short list of questions closes the review, one for each kind of finding, so the owner can hand out the work.

The review reads the export and nothing else. It never visits the site, never opens a page's text, and gives no advice on rankings or traffic. It rewrites, unpublishes, redirects and deletes nothing: the owner decides what happens to each page.

## Who starts the work, and when

The marketing lead or website owner starts it once a quarter, and again before a redesign or a move to a new content management system, when knowing what is on the site decides how much work the move will be. A content manager or marketing coordinator can run it and hand the review to the website owner. The website owner decides what happens to each page and who does it; the page owners update their own pages in the system.

## What they supply

- **The page export from your content management system**, one row per page, with these columns: page ID, address, title, page type, status (published, draft or archived), author, owner, date published, date last updated, meta description and word count. If your headers differ from the defaults, the workflow template stops and asks which column is which.
- **Your site's rules:** how long each page type may go without an update before it counts as stale, which page types must have an owner, the shortest and longest title and description you accept, and how old a draft may get. Where a rule is missing, it uses a stated default and says so.
- **Today's date.**

Leave the page text out of the export. The review needs only the list of pages, and it stops if a column holds page text.

## What comes out

One review in a fixed order: the count that ties to the export; pages past their stale date, grouped by page type; published pages with no owner; titles that are missing, too long, too short or shared; descriptions the same way; drafts older than your limit; likely duplicates by title; records whose dates or word count need checking; and the questions for the website owner. A section with nothing in it says "None." The review closes by saying it was built from the export alone and that nothing was changed.

See the worked example in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Marketing and content](https://fullypowered.ai/functions/marketing-and-content/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-website-content-inventory-review&from=gh-website-content-inventory-review), which owns the website and decides what stays on it.
- [Professional services](https://fullypowered.ai/industries/professional-services/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-website-content-inventory-review&from=gh-website-content-inventory-review), where service pages, insights and event pages pile up over years and each practice expects its pages to stay current.
- [Software technology](https://fullypowered.ai/industries/software-technology/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-website-content-inventory-review&from=gh-website-content-inventory-review), where product, feature and help pages go out of date with every release.
- [Nonprofits](https://fullypowered.ai/industries/nonprofits/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-website-content-inventory-review&from=gh-website-content-inventory-review), where a small team inherits hundreds of campaign and programme pages with no one named against them.
- [Marketing and advertising](https://fullypowered.ai/industries/marketing-and-advertising/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-website-content-inventory-review&from=gh-website-content-inventory-review), where an agency reviews a client's site before quoting a redesign.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-website-content-inventory-review&from=gh-website-content-inventory-review), where a site has grown for a decade and nobody can say what is on it.
- [Acquisitions & integration](https://fullypowered.ai/situations/acquisitions-and-integration/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-website-content-inventory-review&from=gh-website-content-inventory-review), when two companies' sites have to become one and each page needs a decision.

It sits beside [content plan](https://fullypowered.ai/workflows/content-plan/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-website-content-inventory-review&from=gh-website-content-inventory-review), which decides what to write next, and [website findability audit](https://fullypowered.ai/workflows/website-findability-audit/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-website-content-inventory-review&from=gh-website-content-inventory-review), which looks at how saved copies of pages can be reached and read. This one starts from the page list your system already keeps.

## What has to change for your company

Match the column headers to your export, or rename the columns once. Set your stale limit for each page type you use; a news post and a service page age at different speeds. Say which page types need a named owner. Set the title and description lengths your house style accepts. Choose the draft age you consider abandoned. Agree who reads the review, who settles each finding and how page owners report back. It runs in ChatGPT, Claude, Copilot or Gemini, from the export you supply; it needs no connection to your content management system.

## What has been checked

FullyPowered AI wrote this workflow template. It was editorially reviewed on 19 November 2026. It was tried on its example on 19 November 2026 in one run, published with it. Edits after that run, to the format notes, the owner check and the field names in the example, have not been run again. It has not yet been tested in a client environment or as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on last quarter's export, which your website owner knows well, with hard cases written in advance: a renamed column, two pages with the same title, a page updated before it was published, a draft nobody has touched for a year, a page type with no rule. The website owner checks every count against the export before anyone relies on the review. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-website-content-inventory-review&from=gh-website-content-inventory-review) sets those cases up.

- Written by FullyPowered AI.
- Sources and rights reviewed.
- Editorially reviewed on 19 November 2026.
- Package format checked by script on every release.
- Tried once on its example in Claude on 19 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete workflow template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example.
- [TRIAL.md](TRIAL.md): what came out when the template was tried on its example.
- [SKILL.md](SKILL.md): the technical file, for AI products that load packaged instructions from a folder.
- [SOURCES.md](SOURCES.md): what the workflow template drew on, with licences.
- [LICENSE](LICENSE): MIT. Use it, change it, make it yours.

## Start using it

1. Read [EXAMPLE.md](EXAMPLE.md) to see what a good result looks like.
2. Open [TEMPLATE.md](TEMPLATE.md) and set every item under "What to customize" to your own rules, roles and limits.
3. Give your AI assistant the instruction block and the output format from the template, with your own limits in place of the ones the instructions leave open in square brackets. Paste them in as custom instructions in ChatGPT, Claude, Copilot or Gemini, or copy this whole folder into a product that loads `SKILL.md` packages. This folder stands alone; you do not need the rest of the repository.
4. Run it on past work first, using the reviewer checklist and acceptance tests in the template, before anyone relies on it.

## Related workflow templates

- [Content plan](../content-plan/)
- [Website findability audit](../website-findability-audit/)
- [Dashboard and report inventory review](https://fullypowered.ai/workflows/dashboard-inventory-review/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-website-content-inventory-review&from=gh-website-content-inventory-review)

## Make it yours

This workflow template is an example and a starting point. FullyPowered AI adapts it to how your company works, proves it on real work and rolls it out to the roles that use it. We can also build any other workflow for your company, including one that runs several steps, in a Workflow Sprint or a scoped implementation. [Talk with us](https://fullypowered.ai/contact/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-website-content-inventory-review&from=gh-website-content-inventory-review).
