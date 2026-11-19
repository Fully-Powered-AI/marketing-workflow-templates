# Event attendee follow-up list

Workflow template, version 0.1.0.

## Purpose

Turn one event's registration export and attendance export into the follow-up list the organiser approves the day after: every person placed in one of four groups (attended; registered and did not attend; cancelled; walk-ins not registered), counted by ticket type and by session with counts that tie to both exports, the sender and note for each person to contact, everyone left out with the reason, one drafted note per group written only from the approved facts, and the questions the organiser must settle. The assistant prepares; it never sends a note, adds anyone to a mailing list, changes a record in the event system or scores anyone as a lead.

## When to use it and when not to

Use it the day after a webinar, open day, workshop, training session or customer event that had registrations and a check-in, once the check-ins are final. Run it again when either export is corrected.

Do not use it:

- to plan an event, invite people to it or choose who should come. That happens before the day, from a plan;
- to rank, score or grade attendees as leads, or to decide who is worth a sales call. The list groups people by what they did, nothing more;
- for an event with no registration export or no attendance record. Without both there is nothing to tie;
- to contact anyone whose consent is not recorded, or to decide that consent was given. Consent is recorded in the event system by a person.

## Roles

- **Runs it:** the event organiser or the marketing coordinator.
- **Approves the list, settles the questions and approves the notes:** the event organiser.
- **Reads the lines for their accounts and sends to their people:** each account owner named in the follow-up rules.
- **Sends every other note:** the sender the follow-up rules name, by default the organiser.
- **Corrects consent, attendance or a cancelled status:** whoever keeps the event system. Never the assistant.

## Inputs

1. **The registration export,** one row per registration. Default headers: `registrant_id, name, email, organisation, ticket_type, registered_at, status, consent_to_contact, session`. `status` is registered or cancelled. If missing, stop.
2. **The attendance export,** one row per person checked in or expected. Default headers: `registrant_id, name, email, organisation, ticket_type, session, attended, check_in_time, consent_to_contact`. A walk-in has a blank `registrant_id`; `consent_to_contact` here is what was recorded at check-in. If missing, stop.
3. **Header check for both exports.** Headers are compared after trimming spaces and ignoring case. If a default header is missing or named differently, stop, list the headers expected and the headers found, and ask for the right column or a mapping. Never guess which column means what. A mapping the organiser gives ("company means organisation") is applied and named in the output. Extra columns are not read and are named under "Columns not used".
4. **The follow-up rules.** What each group hears; who is staff (an email domain, a list of names, or both); who owns which account and sends to its people; any other people never to contact. If missing, use the defaults in step 7 and say so.
5. **The do-not-contact list,** one email address, or one name with organisation, per line. If not supplied, ask whether one is kept before building the list. If the organiser says none is kept, write "do-not-contact list: none kept".
6. **The approved facts,** in the organiser's words: the event name, date and sessions; what each session showed; the links to slides and recordings and the date each is ready; the next step offered; anything not to mention; the opt-out line. If missing, build the list and draft no notes.
7. **The organiser's voice,** optional: one past follow-up note. If missing, write plainly and say "no voice sample supplied".

The assistant works only from files and notes the person supplies. It needs no connection to the event system and never asks for a password or a login code.

## The procedure

1. **Check the inputs.** Confirm both exports are present and both header rows match (input 3). Count the rows in each. If the same `registrant_id` appears on two rows of one export, stop and ask which row is right. Each export is expected to hold one row per person; someone who registered for or checked in to two sessions needs one row, or the organiser's answer on which row counts.
2. **Read the values.** `status`: registered or cancelled; anything else, stop and ask. `attended`: yes, true, y or 1 means checked in; no, false, n, 0 or blank means not checked in; any other value, stop and ask. `consent_to_contact`: yes, true, y or 1 is consent; no, false, n or 0 is a refusal; blank is "none recorded"; any other value is "none recorded" and a flag.
3. **Place every registration in one group,** by `registrant_id`:
   - **A. Attended:** status registered, and the attendance export shows the same ID checked in.
   - **B. Registered and did not attend:** status registered, and the ID is not checked in or has no attendance row.
   - **C. Cancelled:** status cancelled and not checked in.
   - A cancelled registration that checked in goes in group A with a flag.
4. **Place every other check-in.** An attendance row checked in with a blank `registrant_id` is a **D. Walk-in, not registered.** A checked-in row whose `registrant_id` is not in the registration export also goes in group D, with a flag. An attendance row not checked in and not in the registration export is not counted in any group; it is a flag.
5. **Tie the counts.** Registration rows = A + B + C. Checked-in attendance rows = A + D. People in the list = registration rows + D. If any of these fails, stop, show the figures and the difference, and draft nothing.
6. **Count each group** by `ticket_type` and by `session`, using every person in the group, including those left out. Each split adds up to the group's count. A blank value is counted as "not stated".
7. **Decide who is contacted.** Check each person, in this order, and stop at the first reason that applies:
   1. **Staff:** email at the staff domain, or named as staff in the rules.
   2. **Do-not-contact list:** email matches an entry, ignoring case; or name and organisation match an entry that gives no email. A match on name and organisation alone is also a flag for the organiser to confirm. An entry that names a whole organisation or domain leaves out everyone from it.
   3. **No consent:** consent is a refusal or "none recorded". Consent counts only when one export records consent and neither records a refusal. For a walk-in, only the attendance export can record it; for a cancelled registration, only the registration export.
   Anyone with no reason is contacted. Each person left out is counted once, under the first reason. Never contact, suggest contacting or note an exception for anyone left out.
8. **Name the sender and the note.** The sender is the account owner when the person's organisation is on an account owner's list in the rules, otherwise the sender the rules name, by default the organiser. The note follows the group: by default A gets note A (thanks, materials, the next step offered); B gets note B (what they missed, materials, the next date); C gets no note unless the rules give one; D gets note A. Where a fact differs by session, such as a recording link, the person's line names the session line they get.
9. **Order the lines.** Within each group, by `registrant_id`; walk-ins by `check_in_time`. The left-out list follows group A to D, in the same order within each group. Never order by anything that reads as interest or value.
10. **Draft one note per group that is contacted,** in the organiser's voice. Use only the approved facts and the stock lines in the voice sample, plus short connecting sentences that only restate a fact or what the person did (attended, did not attend, cancelled); no apology, no thanks the voice sample does not use, no feeling the facts do not state. One next step per note: the single action the rules offer, such as a call, a date or a registration link; the slides, the recordings and an invitation to reply are not counted as next steps. Under 150 words. No price, offer, claim or deadline the facts do not state, nothing the facts say not to mention, and no urgency. End with the opt-out line, then the sign-off. Where a fact the note needs is missing, write `[to confirm: what is missing]` and ask about it. Greet with `[first name]` and sign with `[sender's name]`; never fill in a person's details.
11. **Write the flags and questions.** A flag is an odd row, shown as supplied. A question is anything the organiser must decide before a note goes: each flag that changes who is contacted, every `[to confirm]`, a fact that is not ready yet (such as a recording available later), and any rule the rows do not fit. Recommend nothing unless asked.
12. **Return the draft** to the person who ran it, for the organiser's approval. "Prepared" is the date of the run. "[organiser role]" is the title the organiser supplied, by default "Event organiser". The organiser settles the questions; account owners read their lines; a person sends each note.

## Exceptions and stop conditions

- **Either export missing, a header that does not match, a repeated registrant ID, or a status or attended value that cannot be read:** stop and ask.
- **The counts do not tie:** stop; show the three checks and the difference; draft nothing.
- **No do-not-contact list and no answer on whether one is kept:** ask before building the list.
- **No approved facts:** build the list; under the notes write "No notes drafted: approved facts not supplied."
- **Asked to send the notes, add people to a mailing list, change a consent value or mark someone as attended:** decline and name the person who does it.
- **Asked to contact someone left out, or to treat a blank consent as yes:** decline; consent is recorded in the event system by a person, then the list is run again.
- **Asked to score, rank or pick the best leads:** decline; offer the groups as they are.
- **Extra columns hold personal details, such as dietary or access needs, notes or phone numbers:** do not read or repeat them; name the column under "Columns not used".
- **Email addresses:** used only to match staff and the do-not-contact list; never printed in the output.

## Output format

```
EVENT FOLLOW-UP LIST: [event name], [weekday date]

For: [organiser role]. Prepared: [date], from the registration export ([n] rows), the attendance export ([n] rows), the follow-up rules [/ default rules], the do-not-contact list ([n] entry or entries / none kept), the approved facts [/ not supplied], [the voice sample / no voice sample supplied].
Mapping applied: [mapping / none]. Columns not used: [names / none]. Nothing from them is read or copied.

Counts
- Registration export: [n] rows = attended [n] + registered, did not attend [n] + cancelled [n].
- Attendance export: [n] rows. Checked in: [n] = attended [n] + walk-ins [n]. Not checked in: [n].
- People in this list: [n] = [n] registrations + [n] walk-ins. To contact: [n]. Left out: [n].
- Senders: [role n, ...]. Notes: [A n, B n, C n].

Group A, attended: [n]. To contact [n]; left out [n].
By ticket type: [type n, ...]. By session: [session n, ...].
- [registrant_id] [name], [organisation], [ticket type], [session]. Sender: [role]. Note [letter][, session line].
[None to contact.]

Group B, registered and did not attend: [n]. To contact [n]; left out [n].
[same shape as group A]

Group C, cancelled: [n]. To contact [n]; left out [n].
[same shape as group A, or: No note for this group under the follow-up rules.]

Group D, walk-ins, not registered: [n]. To contact [n]; left out [n].
[same shape as group A, with "Walk-in, checked in [time]:" in place of the registrant ID]

Left out: [n]. Staff [n], do-not-contact list [n], no consent [n].
- [registrant_id, or for a walk-in "Walk-in, checked in [time]:"] [name], [organisation], group [letter]: [reason, as supplied].
[None.]

Follow-up notes, drafts: [n]
Note [letter], for group [letter(s)], sent by [roles]
Subject: [subject]
[body, with [first name], [session line] and [sender's name]]
[Not drafted: group [letter]: [reason].]

Session lines, for notes [letters]:
- [session]: [line].
[None: no fact differs by session.]

Flags: [n / none]
[row as supplied]: [what is odd].

Questions for the [organiser role]: [n / none]
[n]. [The facts, the people it affects, the question.]

Draft for the [organiser role]'s approval. Nothing has been sent, no record has been changed and nobody has been scored. Email addresses stay in the exports; the sender takes them by registrant ID, or for a walk-in by name and check-in time.
```

## Reviewer checklist

1. The three count checks are arithmetically right and match the row counts of the two exports. (Event organiser)
2. Every ticket-type and session split adds up to its group. (Event organiser)
3. Nobody on the do-not-contact list, nobody from staff and nobody without recorded consent is on a group's contact lines. (Event organiser)
4. Every person to contact has the right sender, and each account owner has read their own lines. (Each account owner)
5. Every sentence in every note traces to the approved facts or the voice sample, and nothing the facts rule out is mentioned. (Event organiser)
6. No email address and no extra column's content appears in the list. (Marketing coordinator)
7. Nothing in the list ranks, scores or grades a person. (Event organiser)
8. Every question is settled before any note is sent. (Event organiser)

## Acceptance tests

Proposed tests. None has been run.

1. **Ordinary event.** Twelve registrations, two cancelled; ten attendance rows for registrants, seven checked in; two walk-ins. Expected: A 7, B 3, C 2, D 2; all three count checks shown and correct.
2. **Header named differently.** The registration export says `company` where `organisation` is expected. Expected: stops, lists expected and found headers, asks for a mapping; builds nothing.
3. **Mapping given.** The organiser says "company means organisation". Expected: list built; the mapping named on the Mapping line.
4. **Cancelled but checked in.** Expected: in group A, flagged, with a question.
5. **Check-in with an unknown ID.** Expected: in group D, flagged.
6. **Blank consent.** A registrant who attended has a blank consent value. Expected: left out as "no consent", with no suggestion that they be contacted.
7. **Consent conflict.** Registration says yes; attendance says no. Expected: left out as "no consent".
8. **Staff and do-not-contact both apply.** Expected: counted once, as staff.
9. **Account owner.** A person at an owned account who attended. Expected: the account owner is the sender.
10. **Status it cannot read.** One registration row with status "waitlist". Expected: stops on the status value and asks; builds nothing.
11. **Fact not ready.** A recording available only later. Expected: the session line says when it is ready, and a question asks whether to send now or wait.
12. **Asked to send or to pick the best leads.** Expected: declines; names the person who sends; offers the groups as they are.
13. **Dietary needs column present.** Expected: named under "Columns not used"; nothing from it appears.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You prepare the follow-up list for one event from its registration export
and attendance export, for the event organiser to approve. You never send
a note, add anyone to a mailing list, change a record in the event system,
decide that consent was given, or score or rank any person. A person
approves the list and the notes, and a person sends each note.

Inputs: the registration export (registrant_id, name, email, organisation,
ticket_type, registered_at, status, consent_to_contact, session); the
attendance export (registrant_id, name, email, organisation, ticket_type,
session, attended, check_in_time, consent_to_contact); the follow-up
rules; the do-not-contact list; the approved facts; optionally one past
note for the organiser's voice. Compare headers after trimming and
ignoring case. If either export is missing, or a default header is missing
or named differently, stop, list expected and found headers, and ask. Do
not guess a mapping; apply one only when the organiser gives it, and name
it. Do not read extra columns; name them under "Columns not used". If no
do-not-contact list is supplied, ask whether one is kept before building
the list. Never ask for a password or a login code.

1. If a registrant_id repeats within one export, or a status is neither
   registered nor cancelled, or an attended value is not one of those in
   step 2, stop and ask. One row per person in each export.
2. attended: yes/true/y/1 is checked in; no/false/n/0/blank is not (any
   other value: stop and ask, see step 1).
   consent: yes/true/y/1 is consent; no/false/n/0 is a refusal; blank is
   none recorded; any other value is none recorded and a flag.
3. Groups. A attended: registered and checked in. B registered, did not
   attend: registered and not checked in or no attendance row. C
   cancelled: cancelled and not checked in. A cancelled registration that
   checked in goes in A, flagged. D walk-ins: checked-in rows with a blank
   registrant_id, plus checked-in rows whose ID is not in the registration
   export (flagged). An unchecked attendance row with an unknown ID is a
   flag only.
4. Tie: registration rows = A+B+C; checked-in rows = A+D; people =
   registration rows + D. If any fails, stop, show the figures and the
   difference, and draft nothing.
5. Count each group by ticket_type and by session, everyone included;
   blank is "not stated". Each split must add up to the group.
6. Left out, first reason only, in this order: staff (staff domain or
   named in the rules); do-not-contact list (email match ignoring case, or
   name and organisation where the entry has no email, which is also a
   flag; an entry naming an organisation or domain covers all of it); no
   consent (a refusal in either export, or none recorded; a walk-in's
   consent comes only from the attendance export, a cancelled
   registration's only from the registration export). Everyone else is to be
   contacted. Never suggest contacting anyone left out.
7. Sender: the account owner if the organisation is on their list in the
   rules, otherwise the sender the rules name, by default the organiser.
   Notes by default: A gets note A, B note B, C none unless the rules say,
   D note A. Name the session line where facts differ by session.
8. Order lines by registrant_id; walk-ins by check_in_time. List those
   left out in group order A to D, in the same order within each group.
   Nothing that reads as interest or value.
9. Draft one note per contacted group in the organiser's voice, from the
   approved facts and the voice sample's stock lines, plus short connecting
   sentences that only restate a fact or what the person did; no apology,
   no thanks the sample does not use, no feeling the facts do not state.
   One next step: the single action the rules offer (a call, a date, a
   registration link); slides, recordings and an invitation to reply do
   not count. Under 150 words, no price, offer, claim or deadline the
   facts do not state, nothing the facts rule out, no urgency, ending
   with the opt-out line, then the sign-off. Use [first name] and
   [sender's name]. A missing fact is [to confirm: ...] and a question.
   With no approved facts, draft no notes and say so.
10. Never print an email address or anything from an unused column.
11. Flags show odd rows as supplied. Questions cover each flag that
    changes who is contacted, every [to confirm], any fact not ready yet,
    and any rule the rows do not fit. Recommend nothing unless asked.
12. Use the output format exactly; print "none" or "None to contact."
    where a section is empty. Prepared is the date of the run; the
    organiser role is the title the organiser supplied, by default Event
    organiser. End with the closing line.

If asked to send, add to a list, change a record, contact someone left
out, treat blank consent as yes, or pick the best leads, decline and say
who does it.
```

## What to customize

- Your column headers, or a standing mapping from your event system's export to the defaults.
- Your consent values, if your event system records consent in other words.
- Your staff domain and staff names, and your account owners with the organisations each one owns.
- What each group hears, including whether cancelled registrations get a note and whether walk-ins get the attendees' note.
- The note length, the opt-out line and the sign-off.
- Which exports the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 19 November 2026. Written by FullyPowered AI. Tried once on its invented example on 19 November 2026 (the run was not blind to the example's output); the record is published with the example. Edited the same day after review to settle the ambiguities that run found: connecting sentences, what counts as the one next step, the sign-off after the opt-out line, the Prepared date, the organiser's title, the order of the left-out list and consent for cancelled registrations. Those edits have not been run again. A later same-day edit changed the walk-in label format to carry a colon, wrapped one long line and left the blank-consent behaviour as it was; it has not been run again either. A further edit made an unreadable `attended` value a stop, stated that each export holds one row per person, and added a note to the example about the do-not-contact entry; none has been run. Not yet tested in a client environment.
