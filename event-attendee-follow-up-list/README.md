# Event attendee follow-up list

From your registration and attendance exports, a follow-up list with counts that add up and drafted notes. A person approves and sends them.

> [!TIP]
> **Missing a template that is not listed here, or want these customized for your organization? Reach out to us.** This is a template, made to be customized and deployed. FullyPowered AI customizes and builds AI workflows, connects them to your business systems, installs them in your agents and puts them in the hands of the people who own the work. [See Event attendee follow-up list on our website](https://fullypowered.ai/workflows/event-attendee-follow-up-list/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-event-attendee-follow-up-list&from=gh-event-attendee-follow-up-list). Not sure where to start? Email hello@fullypowered.ai and a person will answer.

**Quick start**

1. Read EXAMPLE.md to see what a good result looks like.
2. Copy all of TEMPLATE.md into your assistant, then give it your own inputs, or the invented ones from EXAMPLE.md.
3. Read what comes back. It marks what it checked and what is left for you.

*Workflow template · Marketing and content · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/event-attendee-follow-up-list/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-event-attendee-follow-up-list&from=gh-event-attendee-follow-up-list)*

## The outcome

The morning after an event, the organiser stops cross-checking two spreadsheets by hand and gets one list they can trust. Every person in the two exports lands in exactly one of four groups, and the counts add up to the rows in both exports, so nobody is lost between the files. Each group your rules follow up gets a short note drafted in the organiser's own voice from approved facts only, and people from an account someone already looks after hear from that person.

The list also shows who is left out and why. Nobody is scored or ranked as a lead. The organiser settles the questions and approves the notes; a person sends them. The assistant sends nothing and changes no record.

## Who starts the work, and when

The event organiser or the marketing coordinator starts it the day after the event, once the event system has the final check-ins. It suits any event with a sign-up and a check-in: a webinar, an open day, a workshop, a customer event or a training session. Run it again if the exports are corrected, and the new list replaces the old one.

The organiser approves the list and the notes. Account owners read the lines for their own accounts before anything goes.

## What they supply

- **The registration and attendance exports from your event management system**, with these default columns. Registrations: registrant_id, name, email, organisation, ticket_type, registered_at, status, consent_to_contact, session. Attendance: registrant_id, name, email, organisation, ticket_type, session, attended, check_in_time, consent_to_contact. If a column is named differently, the workflow stops and asks rather than guessing.
- **Your follow-up rules.** Who gets what in each group, who must never be contacted (your staff, by email domain or name), and who owns each account and sends to its people.
- **Your do-not-contact list,** one email address, or one name with organisation, per line. If you keep none, say so; the workflow asks before it builds the list.
- **The approved facts.** What was shown in each session, the links to slides and recordings and when they are ready, what comes next, anything not to mention, and your opt-out line.
- **Your voice, if you have it.** One past follow-up note, for the greeting, tone and sign-off.

The workflow works from files you supply. It needs no connection to your event system, and it never asks for a password or a login code.

## What comes out

One list in a fixed order:

1. **The counts,** tied to both exports: registrations split into attended, did not attend and cancelled; check-ins split into registered attendees and walk-ins.
2. **The four groups,** each counted by ticket type and by session, with every person to contact, the sender and the note they get.
3. **People left out and why,** counted by reason.
4. **The drafted notes,** one per group, with a line for each session where the facts differ.
5. **Flags and questions for the organiser,** such as a cancelled registration that checked in, or a consent value the workflow cannot read.

The list prints no email addresses. Whoever sends takes them from the exports by registrant ID.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Marketing and content](https://fullypowered.ai/functions/marketing-and-content/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-event-attendee-follow-up-list&from=gh-event-attendee-follow-up-list), which runs the events and owns what is said to the people who came.
- [Sales](https://fullypowered.ai/functions/sales/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-event-attendee-follow-up-list&from=gh-event-attendee-follow-up-list), because account owners hear about their own people first and send the notes themselves.
- [Professional services](https://fullypowered.ai/industries/professional-services/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-event-attendee-follow-up-list&from=gh-event-attendee-follow-up-list), where client seminars and briefings are followed up by the partner who owns the relationship.
- [Software technology](https://fullypowered.ai/industries/software-technology/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-event-attendee-follow-up-list&from=gh-event-attendee-follow-up-list), where webinars and customer workshops run every month and the recording link has to reach the right people.
- [Education](https://fullypowered.ai/industries/education/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-event-attendee-follow-up-list&from=gh-event-attendee-follow-up-list), where open days bring registered families and walk-ins through the same door.
- [Nonprofits](https://fullypowered.ai/industries/nonprofits/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-event-attendee-follow-up-list&from=gh-event-attendee-follow-up-list), where supporters' events depend on knowing exactly who agreed to hear from you.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-event-attendee-follow-up-list&from=gh-event-attendee-follow-up-list), when events move from one person's inbox to a regular programme.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-event-attendee-follow-up-list&from=gh-event-attendee-follow-up-list), with account owners, a do-not-contact list and customer events that run every season.

## What has to change for your company

- **One row per person in each export.** If someone registers for or checks in to two sessions, the export must hold one row for them (with the sessions in one cell or one row chosen), because the workflow stops when a registrant ID repeats.
- **Your column names.** Match the defaults to your event system's export once, or give the workflow a short mapping such as "company means organisation".
- **Your groups' rules.** Decide what each group hears, whether cancelled registrations hear anything, and whether walk-ins get the attendees' note.
- **Who is staff, and who owns which account.** Give your email domain and your account owners' lists.
- **Your consent values.** The defaults read yes, no and blank; anything else is treated as no consent and flagged for the organiser.
- **Your opt-out line and sign-off.** Put them in the approved facts so every note carries them.
- **Your platform.** It is written for ChatGPT, Claude, Copilot or Gemini, working from the exports and notes you supply.

## What has been checked

FullyPowered AI wrote this workflow template. It was editorially reviewed on 19 November 2026. It was tried once on its invented example on 19 November 2026; the run was not blind to the example's output, and the record, with the ambiguities it found, is published with the example. Small edits made afterward to settle those ambiguities have not been run again. It has not been tested in a client environment, and has not been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a past event whose follow-up your team remembers, with hard cases written in advance: a column named differently, a cancelled registration that checked in, a walk-in with no consent recorded, a person on the do-not-contact list, a request to send the notes. The organiser checks every count against the two exports before relying on the list. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-event-attendee-follow-up-list&from=gh-event-attendee-follow-up-list) sets those cases up, and [what we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-event-attendee-follow-up-list&from=gh-event-attendee-follow-up-list) describes the record we keep.

- Written by FullyPowered AI.
- Sources and rights reviewed.
- Editorially reviewed on 19 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 19 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete workflow template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example with invented data.
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

- [Event plan](../event-plan/)
- [Email sequence drafting](../email-sequence-drafting/)
- [Text-message opt-in check](../text-message-opt-in-check/)

## Make it yours

This workflow template is an example and a starting point. FullyPowered AI adapts it to how your company works, proves it on real work and rolls it out to the roles that use it. We can also build any other workflow for your company, including one that runs several steps, in a Workflow Sprint or a scoped implementation. [Talk with us](https://fullypowered.ai/contact/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=marketing-event-attendee-follow-up-list&from=gh-event-attendee-follow-up-list).
