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

## Bundle 3

### Exercise 1

```bash
ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git branch
  dev
  ft/bundle-2
  ft/service-redesign
* main

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git switch -C ft/team-page
Switched to a new branch 'ft/team-page'

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/team-page)
$ touch team.html

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/team-page)
$ git add team.html
g
ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/team-page)
$ git commit -m "Adding the team page
> - Creating the page for our team
> "
[ft/team-page a16f52d] Adding the team page - Creating the page for our team
 1 file changed, 11 insertions(+)
 create mode 100644 team.html

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/team-page)
$ git push --set-upstream origin main
Everything up-to-date
branch 'main' set up to track 'origin/main'.

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/team-page)
$ git status
On branch ft/team-page
nothing to commit, working tree clean

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/team-page)
$ git log
commit a16f52dfdf970d0a3a33bc2a865357358b404969 (HEAD -> ft/team-page)
Author: danielerat <davidodo2015@gmail.com>
Date:   Thu Jul 27 11:15:34 2023 +0200

    Adding the team page
    - Creating the page for our team

commit 3eab4a17801f68ea9c36f1379055d1842b03cd68 (origin/main, main)
Author: danielerat <davidodo2015@gmail.com>
Date:   Thu Jul 27 11:11:51 2023 +0200

    Updating the history of the readme.md file

commit 72a0d91b9b8bc70135b2607feff7cad943c0a360
Merge: 1f70cd1 8b27feb
Author: danielerat <davidodo2015@gmail.com>
Date:   Thu Jul 27 11:07:09 2023 +0200

    Merge branch 'ft/service-redesign'

commit 1f70cd1c1681d660fb9b417c10a676aecfd582f8
Author: danielerat <davidodo2015@gmail.com>
Date:   Thu Jul 27 10:57:39 2023 +0200


ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/team-page)
$

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/team-page)
$ git push
fatal: The current branch ft/team-page has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/team-page

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/team-page)
$ git push --set-upstream origin ft/team-page
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 477 bytes | 119.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/team-page' on GitHub by visiting:
remote:      https://github.com/danielerat/git-exercise/pull/new/ft/team-page
remote:
To https://github.com/danielerat/git-exercise.git
 * [new branch]      ft/team-page -> ft/team-page
branch 'ft/team-page' set up to track 'origin/ft/team-page'.

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/team-page)
$ git switch main
bash: $'\302\203\302\203git': command not found

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/team-page)
$ git switch main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (main)
$ git switch -C ft/contact-page
Switched to a new branch 'ft/contact-page'

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/contact-page)
$ git switch ft/team-page
Switched to branch 'ft/team-page'
Your branch is up to date with 'origin/ft/team-page'.

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/team-page)
$ ggit log --oneline --all --graph
bash: $'\302\226git': command not found

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/team-page)
$git log --oneline --all --graph
* a16f52d (HEAD -> ft/team-page, origin/ft/team-page) Adding the team page - Creating the page for our team
* 3eab4a1 (origin/main, main, ft/contact-page) Updating the history of the readme.md file
*   72a0d91 Merge branch 'ft/service-redesign'
|\
| * 8b27feb (origin/ft/service-redesign, ft/service-redesign) Changing the service page - Adding two ninjas
* | 1f70cd1 Adding A ninja from somewhere else in the service page
|/
* b9a0917 Bundle 2 Exercise 1 history
*   a816703 Merge pull request #1 from danielerat/ft/bundle-2
|\
| * eec7020 (origin/ft/bundle-2, ft/bundle-2) Adding the Service Page
| * 531ca3d (origin/dev, dev) Bundle 1 Exercise 2
| * 24552fa Adding the home and about page
| * 5133a5a Adding our home page
| * 7cf6915 Exercise 1 history
|/
* 3af0a29 Initial commit with a readmefile

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/team-page)
$ git switch ft/contact-page
Switched to branch 'ft/contact-page'

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/contact-page)
$ git cherry-pick a16f52d
[ft/contact-page 7ee7885] Adding the team page - Creating the page for our team
 Date: Thu Jul 27 11:15:34 2023 +0200
 1 file changed, 11 insertions(+)
 create mode 100644 team.html

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/contact-page)
$ git log --oneline --all --graph
* 7ee7885 (HEAD -> ft/contact-page) Adding the team page - Creating the page for our team
| * a16f52d (origin/ft/team-page, ft/team-page) Adding the team page - Creating the page for our team
|/
* 3eab4a1 (origin/main, main) Updating the history of the readme.md file
*   72a0d91 Merge branch 'ft/service-redesign'
|\
| * 8b27feb (origin/ft/service-redesign, ft/service-redesign) Changing the service page - Adding two ninjas
* | 1f70cd1 Adding A ninja from somewhere else in the service page
|/
* b9a0917 Bundle 2 Exercise 1 history
*   a816703 Merge pull request #1 from danielerat/ft/bundle-2
|\
| * eec7020 (origin/ft/bundle-2, ft/bundle-2) Adding the Service Page
| * 531ca3d (origin/dev, dev) Bundle 1 Exercise 2
| * 24552fa Adding the home and about page
| * 5133a5a Adding our home page
| * 7cf6915 Exercise 1 history
|/
* 3af0a29 Initial commit with a readmefile

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/contact-page)
$ touch contact.html

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/contact-page)
$ git add contact.html
g
ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/contact-page)
$ git commit -m "Adding the contact page"
[ft/contact-page 1129b47] Adding the contact page
 1 file changed, 11 insertions(+)
 create mode 100644 contact.html

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/contact-page)
$ git push
fatal: The current branch ft/contact-page has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin ft/contact-page

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/contact-page)
$ git push --set-upstream origin ft/contact-page
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 783 bytes | 195.00 KiB/s, done.
Total 6 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/contact-page' on GitHub by visiting:
remote:      https://github.com/danielerat/git-exercise/pull/new/ft/contact-page
remote:
To https://github.com/danielerat/git-exercise.git
 * [new branch]      ft/contact-page -> ft/contact-page
branch 'ft/contact-page' set up to track 'origin/ft/contact-page'.

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/contact-page)
$ git status
On branch ft/contact-page
Your branch is up to date with 'origin/ft/contact-page'.

nothing to commit, working tree clean

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/contact-page)
$ git switch -C ft/faq-page
Switched to a new branch 'ft/faq-page'

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/faq-page)
$ touch faq.html

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/faq-page)
$ git add faq.html
git
ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/faq-page)
$ git commit -m "Creating our faq page"
[ft/faq-page 44717f6] Creating our faq page
 1 file changed, 23 insertions(+)
 create mode 100644 faq.html

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/faq-page)
$ git push --set-upstream origin ft/faq-page
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 621 bytes | 310.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/faq-page' on GitHub by visiting:
remote:      https://github.com/danielerat/git-exercise/pull/new/ft/faq-page
remote:
To https://github.com/danielerat/git-exercise.git
 * [new branch]      ft/faq-page -> ft/faq-page
branch 'ft/faq-page' set up to track 'origin/ft/faq-page'.

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/faq-page)
$ git log --oneline --all --graph
* 44717f6 (HEAD -> ft/faq-page, origin/ft/faq-page) Creating our faq page
* 1129b47 (origin/ft/contact-page, ft/contact-page) Adding the contact page
* 7ee7885 Adding the team page - Creating the page for our team
| * a16f52d (origin/ft/team-page, ft/team-page) Adding the team page - Creating the page for our team
|/
* 3eab4a1 (origin/main, main) Updating the history of the readme.md file
*   72a0d91 Merge branch 'ft/service-redesign'
|\
| * 8b27feb (origin/ft/service-redesign, ft/service-redesign) Changing the service page - Adding two ninjas
* | 1f70cd1 Adding A ninja from somewhere else in the service page
|/
* b9a0917 Bundle 2 Exercise 1 history
*   a816703 Merge pull request #1 from danielerat/ft/bundle-2
|\
| * eec7020 (origin/ft/bundle-2, ft/bundle-2) Adding the Service Page
| * 531ca3d (origin/dev, dev) Bundle 1 Exercise 2
| * 24552fa Adding the home and about page
| * 5133a5a Adding our home page
| * 7cf6915 Exercise 1 history
|/
* 3af0a29 Initial commit with a readmefile

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/faq-page)
$ git revert a16f52d
[ft/faq-page 821ae3a] Revert "Adding the team page"
 1 file changed, 11 deletions(-)
 delete mode 100644 team.html

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/faq-page)
$ git log --oneline --all --graph
* 821ae3a (HEAD -> ft/faq-page) Revert "Adding the team page"
* 44717f6 (origin/ft/faq-page) Creating our faq page
* 1129b47 (origin/ft/contact-page, ft/contact-page) Adding the contact page
* 7ee7885 Adding the team page - Creating the page for our team
| * a16f52d (origin/ft/team-page, ft/team-page) Adding the team page - Creating the page for our team
|/
* 3eab4a1 (origin/main, main) Updating the history of the readme.md file
*   72a0d91 Merge branch 'ft/service-redesign'
|\
| * 8b27feb (origin/ft/service-redesign, ft/service-redesign) Changing the service page - Adding two ninjas
* | 1f70cd1 Adding A ninja from somewhere else in the service page
|/
* b9a0917 Bundle 2 Exercise 1 history
*   a816703 Merge pull request #1 from danielerat/ft/bundle-2
|\
| * eec7020 (origin/ft/bundle-2, ft/bundle-2) Adding the Service Page
| * 531ca3d (origin/dev, dev) Bundle 1 Exercise 2
| * 24552fa Adding the home and about page
| * 5133a5a Adding our home page
| * 7cf6915 Exercise 1 history
|/
* 3af0a29 Initial commit with a readmefile

ilung@Danielerat MINGW64 ~/OneDrive/Desktop/gitExercise (ft/faq-page)
$ git push
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 274 bytes | 137.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/danielerat/git-exercise.git
   44717f6..821ae3a  ft/faq-page -> ft/faq-page

```

## Bundle 4

### Exercise 1

```bash
ilung@Danielerat MINGW64 ~/OneDrive/desktop/gitExercise (ft/home-page-redesign)
$ git switch main
Switched to branch 'main'
Your branch is behind 'origin/main' by 14 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

ilung@Danielerat MINGW64 ~/OneDrive/desktop/gitExercise (main)
$ git remote add git-copy https://github.com/danielerat/git-exercise-copy.git

ilung@Danielerat MINGW64 ~/OneDrive/desktop/gitExercise (main)
$ git status
On branch main
Your branch is behind 'origin/main' by 14 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   home.html

no changes added to commit (use "git add" and/or "git commit -a")

ilung@Danielerat MINGW64 ~/OneDrive/desktop/gitExercise (main)
$ git add home.html

ilung@Danielerat MINGW64 ~/OneDrive/desktop/gitExercise (main)
$ git commit -m "Full poem on the home page"
[main 28c16c9] Full poem on the home page
 1 file changed, 6 insertions(+), 1 deletion(-)

ilung@Danielerat MINGW64 ~/OneDrive/desktop/gitExercise (main)
$ git remote
git-copy
origin

ilung@Danielerat MINGW64 ~/OneDrive/desktop/gitExercise (main)
$ git push
git pushTo https://github.com/danielerat/git-exercise.git
 ! [rejected]        main -> main (non-fast-forward)
error: failed to push some refs to 'https://github.com/danielerat/git-exercise.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

ilung@Danielerat MINGW64 ~/OneDrive/desktop/gitExercise (main)
$ git pull
Auto-merging home.html
CONFLICT (content): Merge conflict in home.html
Automatic merge failed; fix conflicts and then commit the result.

ilung@Danielerat MINGW64 ~/OneDrive/desktop/gitExercise (main|MERGING)
$ git push origin
To https://github.com/danielerat/git-exercise.git
 ! [rejected]        main -> main (non-fast-forward)
error: failed to push some refs to 'https://github.com/danielerat/git-exercise.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

ilung@Danielerat MINGW64 ~/OneDrive/desktop/gitExercise (main|MERGING)
$ git pull
error: Pulling is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

ilung@Danielerat MINGW64 ~/OneDrive/desktop/gitExercise (main|MERGING)
$ git pull
Already up to date.

ilung@Danielerat MINGW64 ~/OneDrive/desktop/gitExercise (main)
$ git push
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 8 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 653 bytes | 653.00 KiB/s, done.
Total 5 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), completed with 2 local objects.
To https://github.com/danielerat/git-exercise.git
   9757c6d..02b07eb  main -> main

ilung@Danielerat MINGW64 ~/OneDrive/desktop/gitExercise (main)
$ git push git-copy
Enumerating objects: 73, done.
Counting objects: 100% (73/73), done.
Delta compression using up to 8 threads
Compressing objects: 100% (70/70), done.
Writing objects: 100% (73/73), 13.94 KiB | 1.16 MiB/s, done.
Total 73 (delta 35), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (35/35), done.
To https://github.com/danielerat/git-exercise-copy.git
 * [new branch]      main -> main

```
