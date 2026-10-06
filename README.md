git add tests/test_rao_input_layout_criteria.py workflow/project/state/frozen_tests.json



git commit -m "task 4 WIP: C11 tests revised for IGM scope, refreeze"



The human re-froze the tests and committed them. The two revised C11 tests currently fail with 'DID NOT RAISE Exception', as expected. Dispatch the Engineer as planned: remove the foreign classification in ncp_loader.py so that a flat profile from another TSO or an unknown TSO is unrecognized and rejected under C3, and the legacy hyphenated ZIP export stays known_irrelevant. First run the whole tests/test_rao_ncp_loader.py, then the two revised C11 tests and the focused C9, C15 and C16 tests (-q -p no:warnings --tb=short). No full suite, no test edits. Also ask QA to note why the criteria count is 16 now and not 17. Do not dispatch the Reviewer yet.
