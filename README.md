Start the next task.

1. Read workflow/project/state/progress.md, workflow/project/backlog.md and workflow/kit/process.md.
2. Take the top OPEN task. That is task 4. It is in attempt 2: attempt 1 was rejected (see D-04 in workflow/project/decisions.md).
3. Follow the process in workflow/kit/process.md, step by step. Do not skip a step.
4. Dispatch QA first. QA must tag every criteria test with its criterion ID (T04-C1 to T04-C16) and add the missing tests for C8 and C9. Then QA runs: python workflow/kit/tools/qa_collect.py --task 4 --freeze
5. Do not dispatch the Engineer until the freeze passes. Commit the frozen tests as a WIP commit.
6. Then dispatch the Engineer, then QA (collector run and report), then the Reviewer, then the Product Owner.
7. Save each report under workflow/project/reports/.
8. Stop and tell me if a step fails, if a file outside the change scope changes, or at N=3 failed attempts.
Write in short sentences and start every report for me with a 3-line SUMMARY.
