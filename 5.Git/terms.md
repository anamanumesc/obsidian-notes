

identifier = code
head = pointer
chhecksum??? =?? e un hash de fisier cod identifier
commit = a change
heckout = change the pointer
tag = human readable checksum

merge = local is the bbranch i merge from. remothe the otther branch



origin = serverul unde se afla (github/gitlab)
staging = adding changes to staging area where we do a final check before commiting them to local repo (GIT ADD)
commit = when our changes are done and we we put them on the loacal repository. a commit = a snapshot of the repo
push = send from local repository to origin
pull = we update local repository with changes from remote origin
branch = different timeline of code 
merge = combine one branch with another 
topic branch = 

working directory = fisiere actuale din folderul meu 
staging area = zona unde sunt modificarile pr commit 
|Tracked – unmodified
tracked unmodified

A=ADDED\
M (MODIFIED) ROSU = WORKING
M VERDE =STAGED
U = unmerged


| git switch         |                                                                           |
| ------------------ | ------------------------------------------------------------------------- |
| git checkout (-b)  | create new branches or change the branch                                  |
| git merge          | combini doua ramuri diferite                                              |
| git merge --squash |                                                                           |
| git merge          |                                                                           |
| git rebase         |                                                                           |
| git status         | outputs the brach im on and the commits i have                            |
| gitkeep, empty dir |                                                                           |
| git stash          |                                                                           |
| git reset          |                                                                           |
| git squash         |                                                                           |
| git add            | adauga fisierele in stating area, gata de commit                          |
| A                  |                                                                           |
| M                  |                                                                           |
| git diff           | Arată diferențele dintre fișierele din working directory și staging area. |
| git diff -- staged | Arată diferențele dintre staging area și ultimul commit.                  |
| git log            | istoricul commiturilor                                                    |

![[Pasted image 20251025143449.png]]


1. merge squash
2. rebase
3. rebase and fast forward merge 
4. cherry pick



---
branches 

develop
feature
resealses
hotfix