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

### Exercise 2

```bash

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git switch -C ft/service-redesign
Switched to a new branch 'ft/service-redesign'

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/se
$ git add .
gt
ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/se
$ git status
On branch ft/service-redesign
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   service.html


ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/se
$ git commit -m "Changing the service page
> - Adding two ninjas "
[ft/service-redesign 8b27feb] Changing the service page - Addi
 1 file changed, 1 insertion(+)

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/se
$ git push
fatal: The current branch ft/service-redesign has no upstream
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/service-redesign

To have this happen automatically for branches without a track
upstream, see 'push.autoSetupRemote' in 'git help config'.


ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/se
$ git push --set-upstream origin ft/service-redesign
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 359 bytes | 119.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local o
remote:
remote: Create a pull request for 'ft/service-redesign' on Git
remote:      https://github.com/danielerat/git-exercise/pull/nsign
remote:
To https://github.com/danielerat/git-exercise.git
 * [new branch]      ft/service-redesign -> ft/service-redesig
branch 'ft/service-redesign' set up to track 'origin/ft/servic'

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/se
$ git switch main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git log
commit b9a0917f8bbe5f8a8fface7baab4db9ccfb9660a (HEAD -> main,
Author: danielerat <davidodo2015@gmail.com>
Date:   Wed Jul 26 12:14:07 2023 +0200

    Bundle 2 Exercise 1 history

commit a816703e8d91ac17f5073bb168818b7079c4d79a
Merge: 3af0a29 eec7020
Author: Moussa Kalam AMZAT <m.amzat@alustudent.com>
Date:   Wed Jul 26 11:54:47 2023 +0200

    Merge pull request #1 from danielerat/ft/bundle-2

    Ft/bundle 2

commit eec7020fe7401d5f86621708469d026ee130f59a (origin/ft/bun)
Author: danielerat <davidodo2015@gmail.com>
Date:   Wed Jul 26 10:56:30 2023 +0200

    Adding the Service Page

commit 531ca3d80f50d352b09eb1b0a46d5b4e92a792ea (origin/dev, d

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working d
        modified:   service.html

no changes added to commit (use "git add" and/or "git commit -"

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git add service.html
g
ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git commit -m "Adding A ninja from somewhere else in the ser
[main 1f70cd1] Adding A ninja from somewhere else in the servi
 1 file changed, 1 insertion(+)"

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 356 bytes | 356.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local o
To https://github.com/danielerat/git-exercise.git
   b9a0917..1f70cd1  main -> main

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git branch
  dev
  ft/bundle-2
  ft/service-redesign
* main

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git switch ft/service-redesign
Switched to branch 'ft/service-redesign'
Your branch is up to date with 'origin/ft/service-redesign'.

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/se
$ git diff main ft/service-redesign
diff --git a/service.html b/service.html
index 251dcb3..68b430d 100644
--- a/service.html
+++ b/service.html
@@ -7,6 +7,6 @@
   </head>
   <body>
     <h1>This is the service page 🥷</h1>
-    <p>New Ninja from somwhere else ! 🥷</p>
+    <h2>Now we are switching to two ninjas 🥷🥷</h2>
   </body>
 </html>

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/se
$ git diff ft/service-redesign main
diff --git a/service.html b/service.html
index 68b430d..251dcb3 100644
--- a/service.html
+++ b/service.html
@@ -7,6 +7,6 @@
   </head>
   <body>
     <h1>This is the service page 🥷</h1>
-    <h2>Now we are switching to two ninjas 🥷🥷</h2>
+    <p>New Ninja from somwhere else ! 🥷</p>
   </body>
 </html>

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/se
$ git switch master
fatal: invalid reference: master

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/se
$ git switch main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git merge ft/servise-redesign
merge: ft/servise-redesign - not something we can merge

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git merge ft/service-redesign
Auto-merging service.html
CONFLICT (content): Merge conflict in service.html
Automatic merge failed; fix conflicts and then commit the resu

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git push
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 372 bytes | 124.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local o
To https://github.com/danielerat/git-exercise.git
   1f70cd1..72a0d91  main -> main
```
