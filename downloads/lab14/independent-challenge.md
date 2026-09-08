# Independent challenge: stop the completed-row leak

Work in the read-only Requests browser you already built in real Power Apps Studio. Use the fictional local fixture for reproducible tests. You may ask an external AI assistant for coaching, but you must gather the evidence, explain the cause, and verify the result.

## Starting fault

Replace only `galRequests.Items` with this deliberately faulty complete formula:

```powerfx
SortByColumns(
    Filter(
        colTestRequests,
        Completed = false && drpStatus.Selected.Value = "All" ||
        Status.Value = drpStatus.Selected.Value
    ),
    "DueDate",
    SortOrder.Ascending
)
```

Do not rebuild the gallery, dropdown, local collection, or selected-record details.

## Clear tests

1. Record expected counts **All 8, Green 3, Yellow 3, Red 2** before testing.
2. Reproduce actual counts **All 8, Green 5, Yellow 4, Red 3**.
3. Use sanitized JSON to prove completed IDs 109–112 and their statuses.
4. Complete Expected, Actual, Formula, and Data in the evidence brief.
5. Explain why the AND/OR grouping leaks a completed row when a color is selected.
6. Make the smallest grouping repair while preserving `SortByColumns` and ascending `DueDate`.
7. Retest All/Green/Yellow/Red, date order, and two different row selections.

## Self-check

- [ ] I gathered evidence before asking AI for a repair.
- [ ] I can explain why `Status.Value` is used.
- [ ] I kept `Completed=false` outside the All-or-matching-status group.
- [ ] I preserved ascending `DueDate` sorting.
- [ ] Counts pass at 8/3/3/2 and completed IDs never appear.
- [ ] Two row clicks still change the visible selected record.
- [ ] I kept the experience read-only.