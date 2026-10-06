python -c "import pathlib;p=pathlib.Path('workflow/project/state/baseline.txt');p.write_text('1b952b5\n')"
python -c "import pathlib;[pathlib.Path(f).write_bytes(pathlib.Path(f).read_bytes().replace(b'f1b6b7d',b'1b952b5')) for f in ['tests/test_repository_scope_guard.py','workflow/project/project.md']]"

python workflow/kit/tools/qa_collect.py --task 4 --freeze

python -m pytest tests/test_repository_scope_guard.py -q -p no:warnings --tb=short

git add workflow/project/state/baseline.txt workflow/project/state/frozen_tests.json workflow/project/project.md tests/test_repository_scope_guard.py
git commit -m "Baseline update to 1b952b5, refreeze task 4 tests"
