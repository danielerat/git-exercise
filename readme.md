# Git Exercises

## Bundle 1

### Exercise 1

```bash
ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise
$ git init
Initialized empty Git repository in C:/Users/ilung/OneDrive/Desktop/gitExercise/.git/

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (master)
$ git branch -M main

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ echo "# Git Exercises" > readme.md

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git add .
warning: in the working copy of 'readme.md', LF will be replaced by CRLF the next time Git touches it

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git commit -m "Initial commit with a readmefile"
[main (root-commit) 3af0a29] Initial commit with a readmefile
 1 file changed, 1 insertion(+)
 create mode 100644 readme.md

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git remote add origin https://github.com/danielerat/git-exercise.git
ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git push -u origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 242 bytes | 242.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/danielerat/git-exercise.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git switch -C dev
Switched to a new branch 'dev'

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git switch -C test
Switched to a new branch 'test'

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (test)
$ git switch dev
Switched to branch 'dev'

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git branch -d test
Deleted branch test (was 3af0a29).
```

### Exercise 2

```bash
ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ echo "" > home.html

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git add home.html
warning: in the working copy of 'home.html', LF will be replaced by CRLF the next time Git touches it

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git commit -m "Adding our home page"
[dev 5133a5a] Adding our home page
 1 file changed, 11 insertions(+)
 create mode 100644 home.html

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git status
On branch dev
nothing to commit, working tree clean

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git stash -m "Home page"
warning: in the working copy of 'home.html', LF will be replaced by CRLF the next time Git touches it
Saved working directory and index state On dev: Home page

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git stash list
stash@{0}: On dev: Home page

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ echo "" > about.html

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git add about.html
warning: in the working copy of 'about.html', LF will be replaced by CRLF the next time Git touches it

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git stash -m "About Page
> "
Saved working directory and index state On dev: About Page


ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ echo "" > team.html

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git add team.html
warning: in the working copy of 'team.html', LF will be replaced by CRLF the next time Git touches it

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git stash -m "Team Page"
Saved working directory and index state On dev: Team Page

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git stash list
stash@{0}: On dev: Team Page
stash@{1}: On dev: About Page
stash@{2}: On dev: Home page

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git stash pop 1
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Dropped refs/stash@{1} (9996f77e2d443102fadd84a12b1fbecdaadcceed)

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git stash list
stash@{0}: On dev: Team Page
stash@{1}: On dev: Home page

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git stash pop 1
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   home.html

Dropped refs/stash@{1} (ba46544e80b0b618036536b41ccaad55159424f4)

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git add .
g
ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git commit -m "Adding the home and about page"
[dev 24552fa] Adding the home and about page
 2 files changed, 12 insertions(+)
 create mode 100644 about.html

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git push
fatal: The current branch dev has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin dev

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git push --set-upstream origin dev
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 8 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (10/10), 1.65 KiB | 337.00 KiB/s, done.
Total 10 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), done.
remote:
remote: Create a pull request for 'dev' on GitHub by visiting:
remote:      https://github.com/danielerat/git-exercise/pull/new/dev
remote:
To https://github.com/danielerat/git-exercise.git
 * [new branch]      dev -> dev
branch 'dev' set up to track 'origin/dev'.

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git stash list
stash@{0}: On dev: Team Page

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git stash pop 0
On branch dev
Your branch is up to date with 'origin/dev'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   team.html

Dropped refs/stash@{0} (8eb4d55c3b2e2f10cd7f18b4cb24d4a2ee6a9643)

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git reset --hard
HEAD is now at 24552fa Adding the home and about page

```

## Bundle 2

### Exercise 1

```bash
ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (dev)
$ git switch -C ft/bundle-2
Switched to a new branch 'ft/bundle-2'

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/bundle-2)
$ echo "" > service.html

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/bundle-2)
$ git add service.html
warning: in the working copy of 'service.html', LF will be replaced by CRLF the next time Git touches it

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/bundle-2)
$ git commit -m "Adding the Service Page"
[ft/bundle-2 eec7020] Adding the Service Page
 1 file changed, 11 insertions(+)
 create mode 100644 service.html

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/bundle-2)
$ ggit push -u origin ft/bundle-2
bash: $'\302\226git': command not found

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/bundle-2)
$ git push -u origin ft/bundle-2
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 465 bytes | 232.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/bundle-2' on GitHub by visiting:
remote:      https://github.com/danielerat/git-exercise/pull/new/ft/bundle-2
remote:
To https://github.com/danielerat/git-exercise.git
 * [new branch]      ft/bundle-2 -> ft/bundle-2
branch 'ft/bundle-2' set up to track 'origin/ft/bundle-2'.

```
