python -m pytest tests/test_rao_input_layout_criteria.py::test_real_input_full_pipeline_end_to_end --runxfail -q -p no:warnings --tb=short 2>&1 | Out-File -Encoding utf8 workflow/project/reports/human-T04-c14-stage.txt

Get-Content workflow/project/reports/human-T04-c14-stage.txt | Select-Object -Last 25

The human ran the C14 failure-stage check. The output is in workflow/project/reports/human-T04-c14-stage.txt. Dispatch QA to update the task 4 report using this file as the C14 stage evidence. QA does not rerun the suite. If QA passes, dispatch the Reviewer.
