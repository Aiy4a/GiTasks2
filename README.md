# Task2 

## Part 1:
- Initialize a new Git repository.
- Create a `README.md` file and push the initial commit to the remote `main` branch.

```bash
mkdir task2
git init
echo "Test" > README.md
git add .
git commit -m "Readme"
git remote add origin git@github.com:Aiy4a/GiTasks2.git
git push -u origin main
```

---

## Branching & Merging
- Create two branches: `dev` and `test`.
- Add files `dev1.py` and `test1.py` in their respective branches.
- Push both branches to the remote.
- Merge changes back into `main`.

```bash
git checkout -b dev
touch dev1.py
git add dev1.py
git commit -m "Add dev1.py"
git push -u origin dev

git checkout main
git checkout -b test
touch test1.py
git add test1.py
git commit -m "Add test1.py"
git push -u origin test

git checkout main
git merge dev
git merge test
git add .
git commit -m "After merge"
git push origin main
```

---

## Removing Branches
- Delete branches locally and remotely after merging.

### Locally:
```bash
git branch -d dev
git branch -d test
```
#### Remotely:
```bash
git push origin --delete dev
git push origin --delete test
```

---

## Switching Branches Without Committing
If you have uncommitted changes and need to switch branches:
- Use `git stash` to save changes temporarily.
- Use `git stash -u` to include untracked files.
- Switch branches and reapply changes with `git stash pop`.

### What I Did
1. Added and committed `notes.py` on `main`.
2. Switched to `temp` and edited `notes.py` again.
3. Tried to checkout `main` → Git refused due to the untracked conflict.
```
error: The following untracked working tree files would be overwritten by checkout:
    notes.py
Please move or remove them before you switch branches.
Aborting
```
4. Used `git stash --include-untracked` to stash both tracked and untracked changes.
5. Successfully switched to `main`.
6. Verified that the version of `notes.py` from `main` was restored (`test1` content).

### Key Command
```bash
git stash --include-untracked
git checkout main
```

## Tagging & Versioning
- Create an annotated tag `v1.7`.
```bash
git tag -a v1.7 -m "version 1.7"
```
- Push it to the remote.
```bash
git push origin v1.7
```
- List tags.
```bash
git tag
```
- Delete tags locally.
```bash
git tag -d v1.7
```
- Delete tags remotely.
```bash
git push origin --delete v1.7
```

---

## Documentation with Images
Add images to your README using Markdown syntax.  

```markdown
![](images/image1.png)
```

