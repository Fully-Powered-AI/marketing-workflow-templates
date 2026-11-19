# Event attendee follow-up list: one trial on the invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-19

The inputs are the invented example in [public/example.md](example.md) (the Brinmoor Customer Workshop: the two exports, the follow-up rules, the do-not-contact list, the approved facts and the voice sample). No client data was used. The run followed the instruction block and the output format in the member template, on those inputs, once.

## An important limit on this trial

The run was meant to be blind to the example's published output. It was not: the example file was opened in one piece before the run, so the output was visible when the list below was produced. The counts, groups and reasons were nevertheless worked out again from the exports, row by row, and checked against the template's rules, and the notes were written fresh. But this trial is not an independent reproduction of the example. Treat the agreement on counts as a check that the rules produce them, not as proof that a cold run would.

## The example after this run, and what was edited

Lines in "What was observed" and "Where the template was ambiguous" below describe the example as it stood at the time of the run. Afterward, following an independent review, the example and the template were edited, and the edited version has not been run again:

- The example's output was changed in these respects to match this run, though small wording differences remain (for example note A's subject, "Thanks for joining" in the example and "Thanks for coming" here, and the year on the last date in the question): its second question (two attendees with no recorded consent) was removed, note B's opening "Sorry we missed you" was replaced with "You were registered ... and we did not see you there", and dates in the notes gained the year, as in this run.
- The template was edited to settle ambiguities 1 to 6 and 8: the sign-off after the opt-out line, connecting sentences, the one next step, the Prepared date, the organiser's title, the order of the left-out list and consent for cancelled registrations.
- After a second review, the template was edited so that an unreadable `attended` value stops the run and so that each export is expected to hold one row per person, and a sentence was added under the example's do-not-contact list saying the entry is one email address, not the organisation. None of this was run again.
- The walk-in label in the output format now carries a colon ("Walk-in, checked in 09:20:"), as this run printed it, and one over-long line in the instruction block was wrapped.
- Ambiguity 7 (no question for an attendee with blank consent) was left as it is on purpose: that person is left out, listed with the reason, and no question is raised. The template, the example and acceptance test 6 agree on it.

The record below is unchanged from the run.

## What came out

EVENT FOLLOW-UP LIST: Brinmoor Customer Workshop, Thursday 12 November 2026

For: Events coordinator. Prepared: Friday 13 November 2026, from the registration export (12 rows), the attendance export (12 rows), the follow-up rules, the do-not-contact list (1 entry), the approved facts, the voice sample.
Mapping applied: none. Columns not used: dietary_needs. Nothing from them is read or copied.

Counts
- Registration export: 12 rows = attended 7 + registered, did not attend 3 + cancelled 2.
- Attendance export: 12 rows. Checked in: 9 = attended 7 + walk-ins 2. Not checked in: 3.
- People in this list: 14 = 12 registrations + 2 walk-ins. To contact: 8. Left out: 6.
- Senders: Account manager 3, Events coordinator 5. Notes: A 4, B 3, C 1.

Group A, attended: 7. To contact 3; left out 4.
By ticket type: Customer 3, Guest 3, Staff 1. By session: Approvals 4, Reporting 3.
- R001 Alma Quist, Organisation A, Customer, Approvals. Sender: Account manager. Note A, Approvals line.
- R002 Bram Dewitt, Organisation A, Customer, Reporting. Sender: Account manager. Note A, Reporting line.
- R005 Esme Rowe, Organisation D, Guest, Reporting. Sender: Events coordinator. Note A, Reporting line.

Group B, registered and did not attend: 3. To contact 3; left out 0.
By ticket type: Customer 1, Guest 2. By session: Approvals 1, Reporting 2.
- R004 Dev Anand, Organisation C, Guest, Approvals. Sender: Events coordinator. Note B, Approvals line.
- R010 Jun Park, Organisation B, Customer, Reporting. Sender: Account manager. Note B, Reporting line.
- R012 Lena Voss, Organisation C, Guest, Reporting. Sender: Events coordinator. Note B, Reporting line.

Group C, cancelled: 2. To contact 1; left out 1.
By ticket type: Customer 1, Guest 1. By session: Approvals 1, Reporting 1.
- R006 Femi Adeyemi, Organisation E, Customer, Reporting. Sender: Events coordinator. Note C.

Group D, walk-ins, not registered: 2. To contact 1; left out 1.
By ticket type: Walk-in 2. By session: Approvals 1, Reporting 1.
- Walk-in, checked in 09:20: Mo Farrant, Organisation F, Walk-in, Approvals. Sender: Events coordinator. Note A, Approvals line.

Left out: 6. Staff 1, do-not-contact list 1, no consent 4.
- R003 Cleo Marsh, Organisation B, group A: no consent; the registration export says no.
- R007 Gus Halloran, Organisation F, group A: on the do-not-contact list.
- R008 Hana Ito, Brinmoor Software, group A: staff; brinmoor.example address.
- R009 Ivo Brandt, Organisation G, group A: no consent; none recorded in either export.
- R011 Kit Lowell, Organisation H, group C: no consent; the registration export says no.
- Walk-in, checked in 13:30: Nell Oduya, Organisation J, group D: no consent; none recorded at check-in.

Follow-up notes, drafts: 3

Note A, for groups A and D, sent by Account manager and Events coordinator
Subject: Thanks for coming to the Brinmoor Customer Workshop

Hi [first name],

Thanks for coming to the Brinmoor Customer Workshop on Thursday 12 November 2026. The slides from both sessions are here: brinmoor.example/workshop-slides.

[session line]

You can book a 30-minute review call with our team at brinmoor.example/review-call. If anything from the day raised a question, reply to this and I'll find the right person.

If you'd rather not hear from us about events, reply and say so and we'll stop.

Best wishes,
[sender's name], Brinmoor Software

Note B, for group B, sent by Account manager and Events coordinator
Subject: Slides and recording from the Brinmoor Customer Workshop

Hi [first name],

You were registered for the Brinmoor Customer Workshop on Thursday 12 November 2026 and we did not see you there. The slides from both sessions are here: brinmoor.example/workshop-slides.

[session line]

The next workshop is online on Thursday 11 February 2027. Registration opens on Tuesday 1 December 2026.

If you'd rather not hear from us about events, reply and say so and we'll stop.

Best wishes,
[sender's name], Brinmoor Software

Note C, for group C, sent by Events coordinator
Subject: The next Brinmoor Customer Workshop

Hi [first name],

You cancelled your place at the Brinmoor Customer Workshop on Thursday 12 November 2026. The next workshop is online on Thursday 11 February 2027, and registration opens on Tuesday 1 December 2026.

If you'd rather not hear from us about events, reply and say so and we'll stop.

Best wishes,
[sender's name], Brinmoor Software

Session lines, for notes A and B:
- Approvals: The recording of the Approvals session, on two-step approval for purchase requests and the new approvals dashboard, is at brinmoor.example/rec-approvals.
- Reporting: The recording of the Reporting session, on scheduled reports and the export to a spreadsheet, will be at brinmoor.example/rec-reporting from Wednesday 18 November 2026.

Flags: none

Questions for the Events coordinator: 1
1. The Reporting recording is not ready until Wednesday 18 November 2026. Four people get the Reporting line: R002 and R005 (note A), R010 and R012 (note B). Should their notes go now, saying when it will be ready, or wait until Wednesday 18 November?

Draft for the Events coordinator's approval. Nothing has been sent, no record has been changed and nobody has been scored. Email addresses stay in the exports; the sender takes them by registrant ID, or for a walk-in by name and check-in time.

## What was observed

- **Every required part was produced:** the header, mapping and unused-columns lines, the three count checks, the four groups with their splits, the left-out list with reasons, three notes, the session lines, flags, questions and the closing line. All three count checks tie, and every split adds up to its group.
- **Nothing made the run stop.** Both exports and all headers matched, no registrant ID repeated, every status was readable, the do-not-contact list and the approved facts were supplied.
- **No email address was printed.** The `dietary_needs` column was named and its content (two vegetarian entries) was not repeated.
- **Differences from the published example.** The groups, counts, senders, contact lines, left-out list and reasons agree, which they would given the exports were arithmetic and the rules are specific. The differences are in wording and one section:
  - The example has two questions; this run has one. The second question in the example (two attendees with no recorded consent) is not required by the template's rule for questions, which asks for a question on "each flag that changes who is contacted", and blank consent is not a flag. The example's question is sensible, but the template does not ask for it.
  - The notes are worded differently. The example's note B opens "Sorry we missed you"; this run avoided it because an apology is not in the approved facts or the voice sample.
  - Left-out reasons for R009 differ slightly in wording ("none recorded in either export" here).
- **Facts in the outputs that are not in the inputs.** None of substance in either. Both lists use only the supplied names, dates and links. Both notes use small connecting phrases of the writer ("we did not see you there", "You cancelled your place", "Sorry we missed you") that are not stated in the approved facts, which is what ambiguity 2 below is about. The "Prepared" date (Friday 13 November 2026) is taken from the date on the approved facts, not from the day of the run.

## Where the template was ambiguous or needed a guess

1. **Sign-off after the opt-out line.** Step 10 says each note ends with the opt-out line, but the voice sample signs off with "Best wishes, [name]". The run put the opt-out line first and the sign-off after it. A reader following "ends with" literally would put the opt-out line last.
2. **Connecting sentences.** Step 10 says every sentence traces to the approved facts or the stock lines in the voice sample. A note needs opening and bridging sentences ("Thanks for coming", "You cancelled your place") that are neither facts nor clearly stock lines. The template does not say how much rewording is allowed.
3. **One next step per note.** Note A, under the rules in the example, carries the slides, the review call and an invitation to reply. The template does not say whether the invitation to reply or the slides count as a "next step".
4. **The "Prepared" date.** The template does not say whether it is the day of the run or the day after the event. The run used the date on the approved facts.
5. **Role names.** The output format says "organiser role"; the template names the event organiser, the example calls the person the events coordinator. The run used the coordinator's title as supplied.
6. **Order of the left-out list.** Step 9 orders the contact lines, but nothing says how to order the left-out list. The run followed group, then registrant ID, then the walk-in last.
7. **Questions about blank consent.** The template does not ask a question for a blank consent on an attendee, only for a flag, so someone who attended with no consent recorded is left out silently apart from the left-out list. The template's own acceptance test 6 is satisfied, but whether to ask is left open.
8. **Cancelled people with a consent value.** A cancelled registrant has only the registration export's consent. The template's consent rule covers walk-ins but not this case explicitly; the run applied the general rule.

No instruction in the template contradicted another in a way that stopped the run, and nothing the template told the assistant to refuse was asked. The refusal paths (send, score, contact someone left out) were not exercised by this example, and neither were the stop conditions; the template's thirteen acceptance tests remain unrun.
