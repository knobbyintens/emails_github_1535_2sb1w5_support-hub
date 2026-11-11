# Support Triage Policy

This repository is the single source of truth for the customer support
operations team. All customer incidents are tracked as GitHub issues in this
repository.

## 1. Intake scope

Triage only genuine customer support requests: bug reports, outages, access
problems, data issues, billing questions, feature requests and how-to questions.

Do **not** triage (create no issue and send no email) for:

- Newsletters and marketing mail (sender local part starts with `newsletter`, or
  the subject contains `newsletter`).
- Invoices, receipts and automated billing notices (sender local part starts
  with `billing`, or the subject contains `invoice` / `receipt`).
- Automated system notifications and status reports (sender local part starts
  with `no-reply`, `noreply` or `no_reply`, or the subject contains
  `status report` / `uptime report` / `weekly digest`).
- Meeting invitations, interview scheduling and other internal HR
  correspondence (subject contains `meeting request` or `interview`).
- Pure thank-you notes (subject begins with `Thanks` or `Thank you`).
- Out-of-office replies and internal announcements.

## 2. Severity classification

Classify every in-scope message in this order; the first matching level wins.
Matching is case-insensitive and applies to the message body text.

1. **Critical (P1)** — body mentions any of: `outage`, `data loss`,
   `cannot access`, `security breach`, `production down`, `completely down`.
2. **High (P2)** — body mentions any of: `error`, `crash`, `fails`, `failure`,
   `degraded`, `slow`, `unable to`, `timeout`.
3. **Normal (P3)** — every other in-scope request.

## 3. Required actions

For every in-scope message, create exactly one issue in this repository:

- Title: `[P<priority>] <message subject>`, using the subject exactly as
  received.
- Body: must state the priority, the customer's email address, and a one-line
  summary of the request.

For P1 (Critical) messages only, also send an escalation email to the primary
on-call engineer listed in `docs/oncall_rotation.md`:

- Subject: `[ESCALATION] <message subject>`
- Body: must reference the issue number and the customer email address.

Do not send escalation mail for P2 or P3 messages.

## 4. Reporting

After triage, produce the local `triage_report.csv` described in the task brief.
