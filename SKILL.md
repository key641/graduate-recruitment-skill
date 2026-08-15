---
name: manage-graduate-recruitment
description: Manage a graduate recruitment workflow across job sources, email, a master application tracker, calendar, and resume files. Use when discovering verified campus or autumn-recruitment roles, scoring job fit, deduplicating a tracker, syncing application stages from recruitment email, reviewing deadlines, or tailoring a resume to an exact JD with user approval before editing the design file.
---

# Manage Graduate Recruitment

Treat the configured master tracker as the source of truth for application status. If setup is incomplete, read [references/setup.md](references/setup.md) and collect only the missing configuration before acting. Read [references/data-rules.md](references/data-rules.md) before writing the tracker. Read [references/resume-tailoring.md](references/resume-tailoring.md) before changing a resume.

## Route the request

- New roles, daily scan, or “检查岗位”: run **Discover jobs**.
- Recruitment messages or “同步进度”: run **Sync email progress**.
- A named company/JD or “定制简历”: run **Tailor resume**.
- “检查求职情况” or weekly review: run **Review pipeline**.
- First use, changed accounts, or missing sources: run **Configure**.

## Configure

1. Ask for the candidate profile, target cohort, target role families, location constraints, and verified resume facts.
2. Ask for the job source, tracker, recruitment mailbox, calendar, and base resume links only when that capability is requested.
3. Record field mappings and user preferences in the user's own workspace or memory. Never write personal values into this reusable skill.
4. Confirm the source of truth, discovery cadence, email cadence, and whether calendar creation is enabled.
5. Default to preparing and tracking applications, never submitting them.

## Discover jobs

1. Read the configured job sources and identify entries added or changed since the last successful scan.
2. Follow the recruitment link and verify the exact JD. Accept only roles explicitly matching the configured graduation cohort and full-time campus/autumn-recruitment scope.
3. Reject internships, social recruitment, prior-year roles, broad job families, and roles inferred only from company announcements unless the user configured them as valid.
4. Require evidence for company, exact title, cohort, location, direct application URL, and current availability. Mark incomplete entries as `待核验`; do not guess the role title.
5. Score fit against the configured candidate profile and cite specific evidence and gaps.
6. Deduplicate against the tracker using normalized company + exact title + job ID. Update an existing row instead of creating a duplicate.
7. Never submit an application.

## Sync email progress

1. Search the configured mailbox since the last successful sync, including forwarded recruitment messages when configured.
2. Extract company, exact role or job ID, stage, required action, deadline, meeting time, timezone, and source thread.
3. Match by job ID first, then company + exact role. Do not merge roles solely because the company matches.
4. Update a stage only when the email is explicit. Preserve later stages when an older email arrives late.
5. Deduplicate by message/thread ID and resulting stage transition.
6. Add a calendar event only for an explicit assessment, interview, or hard deadline when calendar writing is enabled. Ask when time, timezone, or role is ambiguous.
7. Never send email, accept invitations, or submit forms without a separate request.

## Tailor resume

1. Fetch the exact JD and map each requirement to verified evidence from the candidate profile.
2. Choose the closest configured base resume. Treat the design file as a layout template, not the authoritative source of resume facts.
3. Draft the proposed changes in chat first: fit analysis, retained/removed emphasis, and complete replacement copy.
4. Wait for explicit user approval of the content. Do not modify Figma or another design file before approval.
5. After approval, duplicate the base frame/page. Never edit the base version.
6. Name the copy `公司-岗位-YYYYMMDD`. Rewrite only from verified facts; never invent metrics, dates, ownership, tools, domain interest, or experience.
7. Preserve layout, typography, spacing, bullets, and page count. Shorten copy before reducing font size. If a base font is unavailable, stop and agree on a supported replacement before editing.
8. Visually verify the finished copy, then update the tracker with the resume version, link, change summary, and next action.

## Review pipeline

Return a short action list grouped by urgent deadline, high-fit unsubmitted, assessment/interview, awaiting response, and stale. Flag missing JD evidence, duplicate rows, and roles without an approved tailored resume. Recommend no more than five next actions.

## Guardrails

- Use exact job titles and cite the direct JD or recruitment page.
- Preserve user-entered progress, contacts, notes, and resume links unless the current record has been read.
- Do not delete tracker rows automatically; flag invalid evidence and ask before archival.
- Keep failed scans observable by recording the last successful source and remaining uncertainty.
- Keep discovery, resume preparation, and application submission as separate permission boundaries.
- Never expose one user's profile, links, IDs, email rules, or resume facts when configuring another user.
