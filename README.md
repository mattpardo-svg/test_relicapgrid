python -m pytest tests/test_rao_input_layout_criteria.py::test_real_input_full_pipeline_end_to_end --runxfail -q -p no:warnings --tb=short 2>&1 | Out-File -Encoding utf8 workflow/project/reports/human-T04-c14-stage.txt

Get-Content workflow/project/reports/human-T04-c14-stage.txt | Select-Object -Last 25

The human ran the C14 failure-stage check. The output is in workflow/project/reports/human-T04-c14-stage.txt. It shows MilpStageFailure: failed at or after MILP build (KeyError overload_slack_n0), meaning the input stage passes and the failure is at the MILP stage. Dispatch QA to update the task 4 report with this as the C14 evidence. QA does not rerun the suite. If QA passes, dispatch the Reviewer

Select-String -Path workflow/project/reports/human-T04-c14-stage.txt -Pattern "^E ", "Error", "assert", "test_rao_input_layout_criteria.py:" | Select-Object -First 15
