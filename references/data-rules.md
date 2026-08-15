# Tracker write rules

## Identity and deduplication

- Primary key: normalized company + exact role title + job ID.
- If job ID is absent, use normalized company + exact title + official URL.
- Keep separate rows for different roles at the same company.
- Update an existing row for an email stage change; do not create company-only duplicates.

## Evidence required for a verified role

- Exact company and job title
- Explicit configured graduate cohort and recruitment type
- Current direct application URL
- City or `不限`
- Source and verification date

If the role is not explicit, do not infer a title from a broad category.

## Recommended fields

- Company, exact role, job ID, company type, city, URL
- Stage, status, source, priority, fit rationale
- Resume version, next action, deadline, notes
- Evidence URL, verification date, and uncertainty

## Email transitions

- Application receipt -> `已投递`
- Written test or assessment -> `笔试/测评`
- Completed assessment -> `已测评`
- Interview invitation -> exact known interview stage; otherwise record without guessing the round
- Rejection -> `淘汰`
- Offer -> `Offer`

Never downgrade a later stage because an older message was processed late.
