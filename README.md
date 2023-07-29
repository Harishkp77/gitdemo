# gitdemo


create folder ---> mkr foldername

to go location ---> cd foldername

git config --global user.name "Harishkp77"
git config --global user.email "shaarini_harish@outlook.com"

to create git   ---->  git init 


to check the files in folder ---> dir

we can add files in the folder  -- but are untracked. 

to check ---> git status  


staging the file ---->   git add index.html

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
        new file:   index.html
}


to stage all file in folde --->    git add --all or git add -A


after small changes  ----> git status --short

it will show  M index.html


so we add that small change -----> git commit -a -m "Updated index.html with a new line"


to see commit history ----> git log




--------------branch -----------------


to add branch ---- > git branch 'branchname'   example--->   git branch hello-world-images 


to create branch from master ---->git branch hello-world-images * master

after created branch , we have to move current worksp[ace to branch ---->git checkout hello-world-images


it will show Switched to branch 'hello-world-images'


to check the ----> git status 


now do changes and give same proecudre to stag and commit with message name . 

for stagging --->   git add --all

commit --->  git commit -m "Added image to Hello World"



-------- master have some eror but i dont want to distrub the branch, but i want o fix it in master---


so ---->  git checkout -b emergency-fix
it will show Switched to a new branch 'emergency-fix'

changes done then 

given 

D:\MyProjectLibrary\NewFolderTestGit>        ---->   git add index.html

D:\MyProjectLibrary\NewFolderTestGit>        ----->   git commit -m "rectified index file error by emergency branch"
[emergency-fix e652570] rectified index file error by emergency branch
 1 file changed, 6 insertions(+)

----------------now we have to merege emergency to master----------


move to master branch ----->   git checkout master

now to merge branch  ------>   git merge emergency-fix


now we can delete the emergency branch    -------> git branch -d emergency-fix


---------------------------------------------------------------------------------



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


then delete ----->  git branch -d hello-world-images
