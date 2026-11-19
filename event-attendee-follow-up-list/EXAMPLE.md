# Event attendee follow-up list: an invented example

*Illustrative example with invented data.* Brinmoor Software is an invented company that makes purchasing software, and every organisation (Organisation A to Organisation J), person, email address, link and date below is invented. No real firm or person is described. Brinmoor held a half-day customer workshop in two sessions on Thursday 12 November 2026. The next morning, Friday 13 November 2026, its events coordinator supplied the inputs below, in full, and the workflow template returned the list after them.

## The inputs

### 1. The registration and attendance exports from your event management system

The registration export, with one extra column, `dietary_needs`:

```
registrant_id,name,email,organisation,ticket_type,registered_at,status,consent_to_contact,session,dietary_needs
R001,Alma Quist,alma@orga.example,Organisation A,Customer,2026-10-20 09:14,registered,yes,Approvals,
R002,Bram Dewitt,bram@orga.example,Organisation A,Customer,2026-10-20 09:40,registered,yes,Reporting,vegetarian
R003,Cleo Marsh,cleo@orgb.example,Organisation B,Customer,2026-10-21 11:02,registered,no,Approvals,
R004,Dev Anand,dev@orgc.example,Organisation C,Guest,2026-10-22 15:30,registered,yes,Approvals,
R005,Esme Rowe,esme@orgd.example,Organisation D,Guest,2026-10-23 10:05,registered,yes,Reporting,
R006,Femi Adeyemi,femi@orge.example,Organisation E,Customer,2026-10-26 13:20,cancelled,yes,Reporting,
R007,Gus Halloran,gus@orgf.example,Organisation F,Guest,2026-10-27 16:45,registered,yes,Approvals,
R008,Hana Ito,hana@brinmoor.example,Brinmoor Software,Staff,2026-10-28 08:30,registered,yes,Approvals,
R009,Ivo Brandt,ivo@orgg.example,Organisation G,Guest,2026-10-29 12:10,registered,,Reporting,
R010,Jun Park,jun@orgb.example,Organisation B,Customer,2026-11-02 09:55,registered,yes,Reporting,
R011,Kit Lowell,kit@orgh.example,Organisation H,Guest,2026-11-03 14:00,cancelled,no,Approvals,
R012,Lena Voss,lena@orgc.example,Organisation C,Guest,2026-11-05 17:25,registered,yes,Reporting,vegetarian
```

The attendance export. Consent at check-in is recorded only for walk-ins:

```
registrant_id,name,email,organisation,ticket_type,session,attended,check_in_time,consent_to_contact
R001,Alma Quist,alma@orga.example,Organisation A,Customer,Approvals,yes,09:02,
R002,Bram Dewitt,bram@orga.example,Organisation A,Customer,Reporting,yes,13:05,
R003,Cleo Marsh,cleo@orgb.example,Organisation B,Customer,Approvals,yes,08:58,
R004,Dev Anand,dev@orgc.example,Organisation C,Guest,Approvals,no,,
R005,Esme Rowe,esme@orgd.example,Organisation D,Guest,Reporting,yes,13:10,
R007,Gus Halloran,gus@orgf.example,Organisation F,Guest,Approvals,yes,09:15,
R008,Hana Ito,hana@brinmoor.example,Brinmoor Software,Staff,Approvals,yes,08:40,
R009,Ivo Brandt,ivo@orgg.example,Organisation G,Guest,Reporting,yes,13:20,
R010,Jun Park,jun@orgb.example,Organisation B,Customer,Reporting,no,,
R012,Lena Voss,lena@orgc.example,Organisation C,Guest,Reporting,no,,
,Mo Farrant,mo@orgf.example,Organisation F,Walk-in,Approvals,yes,09:20,yes
,Nell Oduya,nell@orgj.example,Organisation J,Walk-in,Reporting,yes,13:30,
```

### 2. The follow-up rules

```
Attended, and walk-ins: thanks, the slides, the recording of their
  session, and the offer of a review call.
Registered, did not attend: the slides, the recording of the session
  they registered for, and the next workshop date.
Cancelled: one short note with the next workshop date.
Account owners: Organisation A and Organisation B belong to the account
  manager, who sends to their people from their own address. Everyone
  else hears from the events coordinator.
Staff: anyone with an @brinmoor.example address. Never contacted.
```

### 3. The do-not-contact list

```
gus@orgf.example
```

The entry is one email address, not the organisation: Gus Halloran is left out, and Mo Farrant of the same organisation, who has a different address, is not.

### 4. The approved facts (events coordinator, 13 November 2026)

```
Event: Brinmoor Customer Workshop, Thursday 12 November 2026, at our
  office. Sessions: Approvals (9:00 to 11:30), Reporting (13:00 to 15:30).
Approvals showed: setting up two-step approval for purchase requests,
  and the new approvals dashboard.
Reporting showed: scheduled reports, and the export to a spreadsheet.
Slides, both sessions: brinmoor.example/workshop-slides
Approvals recording: brinmoor.example/rec-approvals, available now.
Reporting recording: brinmoor.example/rec-reporting, available from
  Wednesday 18 November 2026.
Next workshop: online, Thursday 11 February 2027. Registration opens
  Tuesday 1 December 2026.
Review call: 30 minutes with our team, booked at
  brinmoor.example/review-call.
Do not mention: the price of the approvals dashboard, which is not set.
Opt-out line: "If you'd rather not hear from us about events, reply and
  say so and we'll stop."
```

### 5. The organiser's voice (a past note)

```
Hi [first name],

Thanks for coming to the spring workshop. The slides are here: [link].
If anything from the day raised a question, reply to this and I'll find
the right person.

Best wishes,
[name], Brinmoor Software
```

## The output

**EVENT FOLLOW-UP LIST: Brinmoor Customer Workshop, Thursday 12 November 2026**

For: Events coordinator. Prepared: Friday 13 November 2026, from the registration export (12 rows), the attendance export (12 rows), the follow-up rules, the do-not-contact list (1 entry), the approved facts, the voice sample.
Mapping applied: none. Columns not used: dietary_needs. Nothing from them is read or copied.

**Counts**

- Registration export: 12 rows = attended 7 + registered, did not attend 3 + cancelled 2.
- Attendance export: 12 rows. Checked in: 9 = attended 7 + walk-ins 2. Not checked in: 3.
- People in this list: 14 = 12 registrations + 2 walk-ins. To contact: 8. Left out: 6.
- Senders: Account manager 3, Events coordinator 5. Notes: A 4, B 3, C 1.

**Group A, attended: 7.** To contact 3; left out 4.
By ticket type: Customer 3, Guest 3, Staff 1. By session: Approvals 4, Reporting 3.

- R001 Alma Quist, Organisation A, Customer, Approvals. Sender: Account manager. Note A, Approvals line.
- R002 Bram Dewitt, Organisation A, Customer, Reporting. Sender: Account manager. Note A, Reporting line.
- R005 Esme Rowe, Organisation D, Guest, Reporting. Sender: Events coordinator. Note A, Reporting line.

**Group B, registered and did not attend: 3.** To contact 3; left out 0.
By ticket type: Customer 1, Guest 2. By session: Approvals 1, Reporting 2.

- R004 Dev Anand, Organisation C, Guest, Approvals. Sender: Events coordinator. Note B, Approvals line.
- R010 Jun Park, Organisation B, Customer, Reporting. Sender: Account manager. Note B, Reporting line.
- R012 Lena Voss, Organisation C, Guest, Reporting. Sender: Events coordinator. Note B, Reporting line.

**Group C, cancelled: 2.** To contact 1; left out 1.
By ticket type: Customer 1, Guest 1. By session: Approvals 1, Reporting 1.

- R006 Femi Adeyemi, Organisation E, Customer, Reporting. Sender: Events coordinator. Note C.

**Group D, walk-ins, not registered: 2.** To contact 1; left out 1.
By ticket type: Walk-in 2. By session: Approvals 1, Reporting 1.

- Walk-in, checked in 09:20: Mo Farrant, Organisation F, Walk-in, Approvals. Sender: Events coordinator. Note A, Approvals line.

**Left out: 6.** Staff 1, do-not-contact list 1, no consent 4.

- R003 Cleo Marsh, Organisation B, group A: no consent; the registration export says no.
- R007 Gus Halloran, Organisation F, group A: on the do-not-contact list.
- R008 Hana Ito, Brinmoor Software, group A: staff; brinmoor.example address.
- R009 Ivo Brandt, Organisation G, group A: no consent; none recorded.
- R011 Kit Lowell, Organisation H, group C: no consent; the registration export says no.
- Walk-in, checked in 13:30: Nell Oduya, Organisation J, group D: no consent; none recorded at check-in.

**Follow-up notes, drafts: 3**

**Note A, for groups A and D, sent by Account manager and Events coordinator**

> Subject: Thanks for joining the Brinmoor Customer Workshop
>
> Hi [first name],
>
> Thanks for coming to the Brinmoor Customer Workshop on Thursday 12 November 2026. The slides from both sessions are here: brinmoor.example/workshop-slides.
>
> [session line]
>
> You can also book a 30-minute review call with our team at brinmoor.example/review-call. If anything from the day raised a question, reply to this and I'll find the right person.
>
> If you'd rather not hear from us about events, reply and say so and we'll stop.
>
> Best wishes,
> [sender's name], Brinmoor Software

**Note B, for group B, sent by Account manager and Events coordinator**

> Subject: Slides and recording from the Brinmoor Customer Workshop
>
> Hi [first name],
>
> You were registered for the Brinmoor Customer Workshop on Thursday 12 November 2026, and we did not see you there. The slides from both sessions are here: brinmoor.example/workshop-slides.
>
> [session line]
>
> The next workshop is online on Thursday 11 February 2027, and registration opens on Tuesday 1 December 2026.
>
> If you'd rather not hear from us about events, reply and say so and we'll stop.
>
> Best wishes,
> [sender's name], Brinmoor Software

**Note C, for group C, sent by Events coordinator**

> Subject: The next Brinmoor Customer Workshop
>
> Hi [first name],
>
> You cancelled your place at the Brinmoor Customer Workshop on Thursday 12 November 2026. The next workshop is online on Thursday 11 February 2027, and registration opens on Tuesday 1 December 2026.
>
> If you'd rather not hear from us about events, reply and say so and we'll stop.
>
> Best wishes,
> [sender's name], Brinmoor Software

Session lines, for notes A and B:

- Approvals: The recording of the Approvals session, on two-step approval for purchase requests and the new approvals dashboard, is at brinmoor.example/rec-approvals.
- Reporting: The recording of the Reporting session, on scheduled reports and the export to a spreadsheet, will be at brinmoor.example/rec-reporting from Wednesday 18 November 2026.

**Flags:** none.

**Questions for the Events coordinator: 1**

1. The Reporting recording is not ready until Wednesday 18 November 2026. Four people get the Reporting line: R002 and R005 (note A), R010 and R012 (note B). Should their notes go now, saying when it will be ready, or wait until Wednesday 18 November 2026?

Draft for the Events coordinator's approval. Nothing has been sent, no record has been changed and nobody has been scored. Email addresses stay in the exports; the sender takes them by registrant ID, or for a walk-in by name and check-in time.
