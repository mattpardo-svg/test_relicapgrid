python workflow/kit/tools/qa_collect.py --task 4

python -m pytest tests/test_rao_input_layout_criteria.py::test_real_input_full_pipeline_end_to_end --runxfail -q -p no:warnings --tb=short 2>&1 | Out-File -Encoding utf8 workflow/project/reports/human-T04-c14-stage.txt


The human ran the QA collector for task 4 after the single-IGM C11 implementation and refreshed the C14 stage evidence in workflow/project/reports/human-T04-c14-stage.txt. Dispatch QA to write the report from qa_collect_T04.json, without rerunning the suite. If QA passes, dispatch the Reviewer, who checks in particular C3 and C11 (single-TSO IGM, known_irrelevant for the legacy hyphenated export), the earlier C9 finding, and that every test change is covered by decisions D-11 to D-19. Then the Product Owner decides on acceptance.
