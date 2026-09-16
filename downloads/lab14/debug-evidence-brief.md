# Team Explorer debug evidence brief

Complete this brief before asking an external AI assistant for a replacement
formula. Use fictional records only and remove tenant URLs, secrets, PII, and
unrelated fields.

## Context

- App/screen:
- Control and property:
- Data source:
- Requirement:
- Current search or filter values:
- Studio error text, if any:

## Expected

State one observable result. For the modeled example:

> Selecting Alex Morgan in `galTeamMembers` should show Alex Morgan on
> `scrProfile`.

## Actual

State exactly what happened. Do not write only “it does not work.”

> Selecting Alex Morgan shows Jordan Lee.

## Selected record

Paste the smallest safe projection of the record selected by the gallery:

```json
{
  "ID": 101,
  "Name": "Alex Morgan",
  "JobTitle": "Computer Scientist",
  "Team": "Software Engineering"
}
```

## Variable state

Paste the smallest safe projection of `varSelectedEmployee`:

```json
{
  "ID": 102,
  "Name": "Jordan Lee",
  "JobTitle": "Data Analyst",
  "Team": "Analytics"
}
```

## Current formula

Paste only the relevant current property formula and mark deliberate faults.
For the modeled fault:

```powerfx
// Deliberate fault: this ignores the selected gallery record.
Set(varSelectedEmployee, LookUp(TeamMembers, Name = "Jordan Lee"));
Navigate(scrProfile, ScreenTransition.Cover)
```

## Safe JSON evidence

`JSON` and `Copy` belong in a behavior property such as a button's `OnSelect`.
Use a small projection, not an entire record with image/media fields:

```powerfx
Copy(
    JSON(
        ShowColumns(
            TeamMembers,
            ID,
            Name,
            JobTitle,
            Team,
            Skills,
            Expertise
        ),
        JSONFormat.IndentFour
    )
)
```

If clipboard access is blocked, assign the same JSON expression to
`varDebugJSON`, display it in a multiline text input, and copy the visible
text manually.

## AI request

Ask the AI to diagnose before rewriting. Provide:

1. One most likely hypothesis.
2. One tiny test that could prove or disprove it.
3. The smallest single fix.
4. The exact original test to run again.

For Alex → Jordan, ask whether the fault is in gallery selection, variable
assignment, or profile display. Do not ask for a whole-app rewrite.

## Result

- Hypothesis:
- Tiny-test formula or evidence:
- One change made:
- Retest result:
- Was the hypothesis supported?
- Keep or revert:

Use **Observe → Hypothesize → Test → Learn** and
**Working Version → Make One Change → Test → Keep or Revert**.