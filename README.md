# Git-basic

===================== basic config Git ============================
========= life cycle git ===========

	 -- git init --- --- git add --- - git commit -m ""-
	|				|				|					|					|
working dir		working dir		staging area	Local Repository	Remote Repossitory
(Untracked)


# git init  #--> start check
Initialized empty Git repository in D:/GIT/.git/

# git status
On branch main
....
Untracked files:   #--> have 2 file in directory status Untracked
  (use "git add <file>..." to include in what will be committed)
        app.js
        index.html

# git add index.html   #--> add file to staging area

# git status
...
Changes to be committed:  #--> index.html is in staging area
  (use "git rm --cached <file>..." to unstage)
        new file:   index.html

Untracked files:  	#--> just 1 file in directory status Untracked
  (use "git add <file>..." to include in what will be committed)
        app.js

# git rm --cached index.html   	#--> rm index.html from staging area
rm 'index.html'

# git status  #--> checked status
...
Untracked files: 	#--> after rm index.html that have 2 file in directory status Untracked
  (use "git add <file>..." to include in what will be committed)
        app.js
        index.html

# git add .  #--> add all file to staging area

# git status
On branch main
....
Changes to be committed: 	#--> All files are in staging area
  (use "git rm --cached <file>..." to unstage)
        new file:   app.js
        new file:   index.html

# git commit -m "add file to project"  #--> commit to local Repository
[main (root-commit) e947bc9] add file to project
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 app.js
 create mode 100644 index.html

# git log   #--> Checked commit file
commit e947bc90eccde5d8c80a5d8eeb95bb0df0929e0c (HEAD -> main)
Author: punyawat praepaisan <punyawat@enserv.co.th>
Date:   Mon May 20 10:09:26 2024 +0700

    add file to project  #--> message from commit

*** edit app.js ***

# git status
....
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   app.js   #--> status  app.js edited
...

# git add app.js   #--> add app.js to staging area

# git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   app.js

# git commit -m "change app.js"   #--> commit that saved to local Repository
[main 674a93b] change app.js
 1 file changed, 1 insertion(+)

# git log
commit 674a93b1a9e7ebdbf218547f5a620c506bac5969 (HEAD -> main)
Author: punyawat praepaisan <punyawat@enserv.co.th>
Date:   Mon May 20 10:14:42 2024 +0700

    change app.js   #--> message from commit 2

commit e947bc90eccde5d8c80a5d8eeb95bb0df0929e0c
Author: punyawat praepaisan <punyawat@enserv.co.th>
Date:   Mon May 20 10:09:26 2024 +0700

    add file to project   #--> message from commit 1

# git  log --oneline  	#--> show log in 1 line
674a93b (HEAD -> main) change app.js   	#--> message from commit 2
e947bc9 add file to project  #--> message from commit 1

============ compaire git ==========
# git diff e947bc9 674a93b
diff --git a/app.js b/app.js
index 0b2963a..e69de29 100644
--- a/app.js
+++ b/app.js
@@ -1 +0,0 @@
-console.log("Hello")
\ No newline at end of file

*** edit app.js ***

# git  log --oneline   #--> 3 Version
a4bffd1 (HEAD -> main) add data app.js
674a93b change app.js
e947bc9 add file to project

# git diff 674a93b a4bffd1
diff --git a/app.js b/app.js
index 0b2963a..8821df3 100644
--- a/app.js
+++ b/app.js
@@ -1 +1,2 @@
-console.log("Hello")
\ No newline at end of file
+console.log("Hello")
+console.log("Employee Data")
\ No newline at end of file

============ cancel edit file (check out) ==========
delete all in file app.js

# git checkout app.js
Updated 1 path from the index

====== Git reset =======
touch readme.txt
# git add .
# git reset --hard 674a93b
HEAD is now at 674a93b change app.js

file readme.txt   #--> deleted

===== Git branch =====
-git branch   #---> cerrent branch
-git branch -d <branch name>  #---> Delete branch
-git checkout -b <branch name>   #---> Create && swtich new branch
-git checkout <branch name>  #---> switch branch exits
-git merge <branch name>
==================
# git branch
* main  #--> working on branch main

# git checkout -b add-feature  #--> add new branch
Switched to a new branch 'add-feature'

# git branch
* add-feature
  main

# git checkout main
Switched to branch 'main'

# git branch -d add-feature
Deleted branch add-feature (was 674a93b).

# git checkout -b reported
Switched to a new branch 'reported'

====== How to merge =====
# git checkout main
Switched to branch 'main'

# git branch
* main
  reported

# git merge reported
Updating 674a93b..38ec015
Fast-forward
 index.html | 1 +
 1 file changed, 1 insertion(+)

======== git push ======
login github.com
Create Repository

****** new project ****
# echo "# Git-basic" >> README.md
# git init
# git add README.md
# git commit -m "first commit"

****** exits project  ******
# git branch -M main
# git remote add origin https://github.com/manapp2/Git-basic.git
# git push -u origin main
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 8 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (12/12), 1.02 KiB | 349.00 KiB/s, done.
Total 12 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/manapp2/Git-basic.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

**** Check in github.com ******
****** send to myteam ******
# git remote add origin https://github.com/manapp2/Git-basic.git
# git branch -M main
# git push -u origin main
