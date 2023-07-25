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
