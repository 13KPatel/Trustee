Trust Manager: app, tests and cross-checks (October 2026)

index.html            The app
tests-*.js            548 tests: tax (66), IHT (66), CGT (47), compliance (40), data (48), sync (21), lay-trustee walkthrough, Forms tab and Compliance trim (65), forms and tax-return notice (54), Home screen (29), colours (22), layout (54), income tax review fixes (36)
reference_*.py +      Independent cross-checks (Python reference vs the app):
crosscheck*.js        IHT, income tax, CGT, deadlines. reference_income.py was rewritten from the legislation in October 2026 (it had shared two of the app's errors); it now disagrees with the old version on 9,661 of 30,400 figures and agrees with this one on all of them.

Run everything:  npm i jsdom@24
                 for f in tests-*.js; do node $f | tail -1; done
                 python3 reference_iht.py && node crosscheck.js   (same pattern for _income, _cgt, _dates)
Also run with TZ=Europe/London in front of each command.
Methods, test cases and open questions: "Trust Manager: tax calculation tests and methods" doc.
