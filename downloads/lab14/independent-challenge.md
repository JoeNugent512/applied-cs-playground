# Independent challenge: Requests browser

Build in real Power Apps Studio, but use the fictional local fixture for reproducible tests. Keep the app read-only.

## Requirements

- One visible gallery named `galRequests`.
- One collection named `colTestRequests` loaded from the supplied fixture.
- Incomplete records only, sorted by `DueDate` ascending.
- One classic dropdown named `drpStatus` with All, Green, Yellow, Red.
- Status filtering that never removes the incomplete-only rule.
- A selected-record variable named `varSelectedRequest`.
- A separate visible detail area that changes when different rows are selected.
- One deliberate bug, one sanitized JSON capture, one evidence brief, one small repair, and a retest.
- No `Patch`, submit, or server write.

## Clear tests

1. The fixture contains 12 rows; the browser shows 8 for All.
2. Green shows 3: IDs 101, 104, 107.
3. Yellow shows 3: IDs 102, 105, 108.
4. Red shows 2: IDs 103, 106.
5. Each filtered set remains in ascending `DueDate` order.
6. Select two different rows; the external detail labels visibly change.
7. Completed IDs 109–112 never appear in any dropdown state.
8. The deliberate bug has recorded Expected, Actual, Formula, and Data.
9. The JSON projection contains only fields needed for diagnosis and was inspected before sharing.
10. One small repair passes the original failing test.

## Self-check

- [ ] I gave AI context and schema before asking for code.
- [ ] I asked AI to clarify material unknowns.
- [ ] I can explain why `Status.Value` is used.
- [ ] I preserved `Completed=false` around the All-or-status condition.
- [ ] I proved the selected record changes.
- [ ] I diagnosed from evidence instead of blindly replacing the formula.
- [ ] I understand that local collection success does not prove live SharePoint connector or delegation behavior.
- [ ] I kept the experience read-only.