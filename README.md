create folder ---> mkr foldername

to go location ---> cd foldername

git config --global user.name "Harishkp77"
git config --global user.email "shaarini_harish@outlook.com"

to create git ----> git init

to check the files in folder ---> dir

we can add files in the folder -- but are untracked.

to check ---> git status

staging the file ----> git add index.html

(before and after staging){
D:\MyProjectLibrary\NewFolderTestGit>git status
On branch master

No commits yet

Untracked files:
(use "git add <file>..." to include in what will be committed)
index.html

nothing added to commit but untracked files present (use "git add" to track)
D:\MyProjectLibrary\NewFolderTestGit>git add index.html

D:\MyProjectLibrary\NewFolderTestGit>git status
On branch master

No commits yet

Changes to be committed:
(use "git rm --cached <file>..." to unstage)
new file: index.html
}

to stage all file in folde ---> git add --all or git add -A

after small changes ----> git status --short

it will show M index.html

so we add that small change -----> git commit -a -m "Updated index.html with a new line"

to see commit history ----> git log

--------------branch -----------------

to add branch ---- > git branch 'branchname' example---> git branch hello-world-images

to create branch from master ---->git branch hello-world-images \* master

after created branch , we have to move current worksp[ace to branch ---->git checkout hello-world-images

it will show Switched to branch 'hello-world-images'

to check the ----> git status

now do changes and give same proecudre to stag and commit with message name .

for stagging ---> git add --all

commit ---> git commit -m "Added image to Hello World"

-------- master have some eror but i dont want to distrub the branch, but i want o fix it in master---

so ----> git checkout -b emergency-fix
it will show Switched to a new branch 'emergency-fix'

changes done then

given

D:\MyProjectLibrary\NewFolderTestGit> ----> git add index.html

D:\MyProjectLibrary\NewFolderTestGit> -----> git commit -m "rectified index file error by emergency branch"
[emergency-fix e652570] rectified index file error by emergency branch
1 file changed, 6 insertions(+)

----------------now we have to merege emergency to master----------

move to master branch -----> git checkout master

now to merge branch ------> git merge emergency-fix

now we can delete the emergency branch -------> git branch -d emergency-fix

---

back to branch -----> git checkout hello-world-images

added new iamge and given add and commit command...

for this branch merege we have to do same as emergency branch above.

git checkout master

git merge hello-world-images
asking ---->
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.

go to editor and accept which one u want ----

then ---> git add index.html

--------->git status

--->git commit -m "merged with hello-world-images after fixing conflicts"

then delete -----> git branch -d hello-world-images

---

---

---

---

github connect ------->

1.  add remoto localtion to ur local repo -------> git remote add origin https://github.com/Harishkp77/gitdemo.git

2.  push the local repo to remoto repo ---- > git push --set-upstream origin master

then ->

i added readme file in github

so whenever we start we should update our local repo from remote

for that

1.  Git Fetch

----------------> git fetch origin

then to check --------->git status

it shows Your branch is behind 'origin/master' by 1 commit, and can be fast-forwarded.
(use "git pull" to update your local branch)

to cross check ----> git log origin/master

commit 3f8892881df4234214f49fefc39ea315a9d002ca (origin/master)
Author: Harishkp77 <137972179+Harishkp77@users.noreply.github.com>
Date: Sat Jul 29 20:22:41 2023 +0530

    Create README.md

commit 6f4e1be260c99cc80313097f815da64358212a32 (HEAD -> master)
Merge: e652570 f951fd2
Author: Harishkp77 <shaarini_harish@outlook.com>
Date: Sat Jul 29 14:15:40 2023 +0530

    merged with hello-world-images after fixing conflicts

commit f951fd2ee76aa209c07fd3aa43ae644ad7d424f9
Author: Harishkp77 <shaarini_harish@outlook.com>
Date: Sat Jul 29 14:09:07 2023 +0530

    added new image

commit e652570c51bb4fb0e1ffd95d0dcbee6bc54e1757
Author: Harishkp77 <shaarini_harish@outlook.com>
Date: Sat Jul 29 14:02:09 2023 +0530

fetch will show the updates changed ...

now after fetch we should merge ---------------> git merge origin/master
Updating 6f4e1be..3f88928
Fast-forward
README.md | 147 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
1 file changed, 147 insertions(+)
create mode 100644 README.md

-----merge combines the current branch, with a specified branch.-------

then check status-----> git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean

for the above 2 condition of fetch and merge --> we can use pull command----

let see for pulll

--------------> git pull origin

remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 1.61 KiB | 2.00 KiB/s, done.
From https://github.com/Harishkp77/gitdemo
3f88928..13ada80 master -> origin/master
Updating 3f88928..13ada80
Fast-forward
README.md | 136 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++--
1 file changed, 133 insertions(+), 3 deletions(-)

thats all it will change ur local repo up to date

now from local we can change and push

i have altered html page .

1.---> git commit -a -m "Updated index.html"

2. check status ----> git status
   On branch master
   Your branch is ahead of 'origin/master' by 1 commit.
   (use "git push" to publish your local commits)

nothing to commit, working tree clean

3.now push to remoto repo --------> git push origin-----

---------------created branch in git hub ----------

going to pull to local ----->git pull

now check status -----> git status

---------->git branch its shows only local

it shows

- master

------------> git branch -a ut will shows remote and local both
it shows

- master
  remotes/origin/html-skeleton
  remotes/origin/master

----------------> git checkout html-skeleton shifted to html skeleton branch

----------------> now pull request ----------> git pull

------------------------------done --------------------------------------
