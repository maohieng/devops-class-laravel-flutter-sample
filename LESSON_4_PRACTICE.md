# DevOps 005 - Lesson 4 Practice

## I. Reuse your previous group repository
1. Create a script in `scripts/check-feature-txt.sh`

```bash
set -eu
for file in *.txt; do
  test -f "$file" || { echo "No topic files found"; exit 1; }
  echo "Checking $file"
  grep -Eq '^Name:[[:space:]]*[^[:space:]]' "$file" || {
    echo "Missing Name: in $file"
    exit 1
  }
done
echo "All topic checks passed"
```

2. Create a Github Workflow in `.github/workflows/ci.yml` 

```bash
name: Team guide CI
on: [push, pull_request, workflow_dispatch]
permissions:
  contents: read
jobs:
  check:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v6
      - name: Test topic files
        run: bash scripts/check-feature-txt.sh
      - name: Build guide bundle
        run: |
          mkdir -p dist
          tar -czf dist/team-guide.tgz *.txt
          tar -tzf dist/team-guide.tgz

```

3. Push to new branch `ci/setup` 
```
git switch -c ci/setup
git add scripts/check-feature-txt.sh .github/workflows/ci.yml
git commit -m "Add team guide CI checks"
git push -u origin ci/setup
```

4. Check your github action, fix it if the job failed

## II. Submit Your Own Repository URL