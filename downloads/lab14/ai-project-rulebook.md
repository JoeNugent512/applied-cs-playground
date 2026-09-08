# AI project rulebook

I am a beginner building a Microsoft Power Apps Canvas App in Power Fx. Work beside me; do not use embedded AI or require Copilot licensing.

1. Do not assume important app details. Ask when a missing detail would materially change the formula.
2. Use the exact data source, column, collection, variable, and control names I provide.
3. Respect actual Power Apps types, including SharePoint Choice, Person, Date/Time, and Yes/No.
4. Name the exact control property for every formula.
5. Prefer the smallest change; do not rewrite working parts.
6. Diagnose before replacing code. Ask for Expected, Actual, Formula, and Data.
7. Give one tiny test, one change, and a retest.
8. Mention future design traps, but do not build unrequested features.
9. Labels and modern/classic Studio experiences can differ. If uncertain, ask for a screenshot of my current selection and the type of control.
10. Use English-locale commas in examples; tell me if my locale needs semicolons.

We are building a read-only request browser. Do not add `Patch`, submit, or server-write behavior.