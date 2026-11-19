---
name: "event-attendee-follow-up-list"
description: "Turn one event's registration export and attendance export into the follow-up list the organiser approves the day after: every person placed in one of four groups (attended; registered and did not attend; cancelled; walk-ins not registered), counted by ticket type and by session with counts that tie to both exports, the sender and note for each person to contact, everyone left out with the reason, one drafted note per group written only from the approved facts, and the questions the organiser must settle. The assistant prepares; it never sends a note, adds anyone to a mailing list, changes a record in the event system or scores anyone as a lead."
license: "MIT"
metadata:
  version: "0.1.0"
  publisher: "FullyPowered AI"
  template: "Event attendee follow-up list"
---

# Event attendee follow-up list

This is the technical file for a FullyPowered workflow template. It carries the instructions an AI product follows. The complete template, with roles, inputs, exceptions, the reviewer checklist, acceptance tests and what to customize, is in [TEMPLATE.md](TEMPLATE.md). A worked example with invented data is in [EXAMPLE.md](EXAMPLE.md).

## Instructions

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

## Before relying on it

Decide every item under "What to customize" in TEMPLATE.md and set the limits the instructions in this file leave open, written in square brackets such as [N], to your own. Then run the acceptance tests in TEMPLATE.md on past work. A person starts this work, supplies the inputs and decides what happens with the result.
