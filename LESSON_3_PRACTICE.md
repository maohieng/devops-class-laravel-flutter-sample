# DevOps 005 - Lesson 3 Practice

## Group Repo Owner
1. Create a public repository named: **`devops-005-lesson-3`**
2. Create a README.md contains **your members name**
3. **Share** repository link to your member
4. **Make sure** all members have forked your repository

## Group Member & Owner
1. **Clone** the forked repository from your Group Owner
  ```sh
  git clone YOUR-HTTPS-OR-SSH-GITHUB-URL
  ```
2. **Choose one task** from below
   - commit.txt -> `feature/commit` 
   - branch.txt -> `feature/branch` 
   - push.txt -> `feature/push`
   - pull-request.txt -> `feature/pull-request`
   - merge.txt -> `feature/merge`
   - tag.txt -> `feature/tag`
4. Create **your task branch**
  For example, if your task is `commit.txt`:
   ```sh
   git switch -c feature/YOUR-NAME-commit
   ```
6. Create your **task file**
  For example, `commit.txt`.
7. Push your work branch
   For example, if your task is `commit.txt`:
   ```sh
   git add commit.txt

   git commit -m "Add commit feature"

   git push -u origin feature/commit
   ```
8. Open a pull request.
  For example, `commit.txt`:
  1. On GitHub, open Pull requests → New pull request.
  2. Choose base: `main` and compare: `feature/commit`.
  3. Check Files changed: only the intended `commit.txt` change.
  4. Title: Add commit feature.
  5. Create the pull request and show it to your group.
9. Review together, then merge
10. Sync main
  ```sh
  git switch main

  git pull --ff-only origin main
  ```
## Group Owner: publish a tag
```sh
git tag -a v0.1.0 -m "Lesson 3 completed"

git push origin v0.1.0
```
