1. ce face git switch??? care edif intre git switch dsi git checkout??
2. unde adaug tags pe ce branch?
3. unde lucreaza fiecare ? developerii lucreaza pe dev, testerii pe relese? unde devops
4. who manages the hotfix
5. what is the role of devops
6. what is the branching strategy used for agile
7. in companii care workflows sunt folosite
8. cum sunt rezolvate conflictele si cinele rezolva? diferentele de cod
9. eu cand vreau sa dau release la cod. de pe ce branch fac asta? de unde?
10. cum fucntioneaz aun merge request
11. feature toggles vs tags

12. explain this: **DevOps:** gestionează **integrarea (merge în main/release)**, **build pipelines**, **deployment**, **monitorizare** și **rollback**.
13. explain this DevOps este **liantul între development și operations** — automatizează tot ce ține de livrarea codului:


14. CARE E DIFERENTA INTR EPULL SI MERGE?? e acelasi lucru dar alti termeni?

- gestionează pipeline-urile CI/CD (build, test, deploy);
    
- administrează infrastructura (on-prem, cloud, Kubernetes);
    
- monitorizează performanța și uptime-ul aplicației;
    
- automatizează rollback, scaling și configurarea environment-urilor;
    
- implementează GitOps, IaC (Infrastructure as Code), observabilitate și securitate în pipeline-uri.



- cand adaug gitingore. acesta mai lasa fisierele a fie salvate in staging area (index)?

1. fit status vs git log 
2. `origin/feature/x`, ce inseamna acek x? e unbranch din feature?
3. explica toate optiunile cu push . gen ce e -u? ce alt tip de comenzi am? da mi exemple e face fiecare. si cu push si cu pull
4. care sunt motive des intalnite pt care nu mi merge pull/push
5. cum adaug tags?




6. Git objects
7. How Git works = **Git hooks** are custom scripts that run automatically when specific Git events occur.
8. Hooks
9. Commit and tag
10. References




```bash

git clone <gitlab_repo_url>                           # copiaza repo-ul de pe gitlab intr-un nou director local

cd <repo_name>                                        # intra in directorul proaspat clonat

git checkout -b master                                # creeaza si comuta pe o noua ramura numita master (-b = create branch si checkout)

mkdir -p folder1 folder2 folder3                      # creeaza directoarele; -p nu da eroare daca exista si creeaza parintii lipsa

touch folder2/file2 folder3/file31 folder3/file32     # creeaza fisierele goale la caile date

printf "folder2/file2\nfolder3/\n" >> .gitignore      # adauga regulile in .gitignore (>> = append la finalul fisierului)

git add .gitignore                                    # pune .gitignore in staging (pregatit pentru commit)

git commit -m "add gitignore"                         # creeaza un commit cu ce e in staging (-m seteaza mesajul commitului)

git push -u origin master                             # impinge ramura master la remote origin (-u seteaza upstream/tracking pentru push/pull viitoare)

touch folder1/.gitkeep                                # adauga un placeholder ca sa poata fi versionat folder1 gol

git add folder1/.gitkeep                              # pune fisierul .gitkeep in staging

git commit -m "keep empty folder1"                    # salveaza commitul care mentine folder1 in repo

git push                                              # impinge commitul curent pe upstreamul setat

git checkout -b topic master                          # creeaza si comuta pe ramura topic pornind din master

touch file1.txt                                       # creeaza fisierul file1.txt

git add file1.txt                                     # pune file1.txt in staging

git commit -m "add file1"                             # salveaza commitul cu file1.txt

git checkout master                                   # revine pe ramura master

git merge topic                                       # uneste topic in master; daca master nu are commituri noi, e fast-forward (nu se creeaza merge commit)

git log --oneline --graph --decorate --all            # afiseaza istoricul: --oneline scurt, --graph deseneaza graful, --decorate arata heads/tags, --all include toate ramurile

touch file2.txt                                       # creeaza file2.txt pe master

git add file2.txt                                     # pune file2.txt in staging

git commit -m "add file2 on master"                   # salveaza commitul cu file2.txt pe master

git checkout topic                                    # comuta pe topic

echo "change" >> file1.txt                            # adauga text la finalul file1.txt (>> = append)

git add file1.txt                                     # pune modificarile din file1.txt in staging

git commit -m "update file1 on topic"                 # salveaza commitul de pe topic

git checkout master                                   # revine pe master

git merge --no-ff topic                               # merge care creeaza intotdeauna un merge commit (--no-ff = dezactiveaza fast-forward)

git log --oneline --graph --decorate --all            # vezi graful cu merge commitul creat mai sus

echo "master edit" >> file1.txt                       # modifica file1.txt pe master (va provoca conflict ulterior)

git add file1.txt                                     # pune modificarile pe master in staging

git commit -m "master edits file1"                    # commit pe master

git checkout topic                                    # comuta pe topic

echo "topic edit" >> file1.txt                        # modifica si pe topic acelasi fisier (pregateste conflictul)

git add file1.txt                                     # stage pe topic

git commit -m "topic edits file1"                     # commit pe topic

git checkout master                                   # revine pe master

git merge topic                                       # incearca unirea; apare conflict in file1.txt pentru ca ambele ramuri au modificat liniile

git checkout --theirs file1.txt                       # rezolva conflictul alegand varianta "theirs" (ramura adusa prin merge, adica topic, in contextul curent)

git add file1.txt                                     # marcheaza fisierul ca rezolvat si il pune in staging

git commit -m "resolve conflict using topic version"  # finalizeaza merge-ul cu un commit de rezolvare

git log --oneline --graph --decorate --all            # verifica istoricul cu merge si rezolvarea conflictului

git push                                              # impinge istoricul actual al lui master pe remote

git checkout topic                                    # comuta pe topic

git rebase master                                     # reaseaza commiturile din topic peste varful lui master (istoric mai liniar)

echo "more changes" >> file1.txt                      # inca o modificare pe topic

git add file1.txt                                     # stage pe topic

git commit -m "more changes on topic"                 # commit pe topic

git push -u origin topic                              # impinge ramura topic pe remote (-u seteaza upstream pentru topic)


```