# Fundamentale

|Scop|Comandă|Explicație scurtă|
|---|---|---|
|inițializează un repo local|`git init`|creează folderul `.git`|
|clonează un repo existent|`git clone <url>`|ia o copie locală a unui repo GitLab/GitHub|
|verifică statusul|`git status`|vezi fișiere modificate, staged, untracked|
|adaugă fișiere în staging|`git add <fisier>`|pregătește fișierul pentru commit|
|adaugă tot|`git add .`|adaugă toate modificările curente|
|creează un commit|`git commit -m "mesaj"`|salvează snapshot-ul în istoric|
|vezi istoricul|`git log`|lista commit-urilor|
|vezi pe scurt istoricul|`git log --oneline --graph --decorate --all`|grafic simplificat|
|anulează modificările dintr-un fișier|`git restore <fisier>`|revine la ultima versiune salvată|
|scoate fișiere din staging|`git restore --staged <fisier>`|le lasă modificate, dar nelistate pentru commit|

---

#  Lucrul cu remote (GitLab)

|Scop|Comandă|Explicație|
|---|---|---|
|adaugă remote|`git remote add origin <url>`|conectează repo local la GitLab|
|vezi remote-urile|`git remote -v`|verifică legătura cu GitLab|
|trimiți schimbările|`git push -u origin main`|prima dată setează upstream|
|trimiți schimbările următoare|`git push`|după ce upstream e setat|
|aduci modificări din remote|`git pull`|actualizează localul cu ce e pe GitLab|
|descarcă fără a fuziona|`git fetch`|doar aduce, nu schimbă localul|
|sincronizează complet|`git pull origin main --allow-unrelated-histories`|utile la repo-uri divergente|

# Branching și Merging

|Scop|Comandă|Explicație|
|---|---|---|
|creează o ramură nouă|`git branch topic`|doar creează|
|comută pe alt branch|`git checkout topic`|te mută pe branch-ul respectiv|
|creează și comută direct|`git checkout -b topic`|scurtătură comună|
|vezi ramurile existente|`git branch -vv`|vezi și track-urile remote|
|unește topic în main (fast-forward)|`git merge topic`|dacă main e nemodificat|
|unește cu commit explicit|`git merge --no-ff topic`|păstrează commit de merge|
|rezolvă conflicte|`git add <fisier>` + `git commit`|după editarea manuală|
|șterge o ramură|`git branch -d topic`|local; `-D` forțat|

---

# Rebase, Reset, Restore (manipularea istoricului)

|Scop|Comandă|Explicație|
|---|---|---|
|aduci main în topic|`git rebase main`|aplică commit-urile topic peste main|
|continui rebase după conflict|`git rebase --continue`|după rezolvare|
|anulezi rebase-ul|`git rebase --abort`|revii la starea anterioară|
|rescrii istoricul local|`git reset --hard origin/main`|aliniază 100% la remote|
|muți HEAD cu un commit înapoi|`git reset HEAD~1`|anulează ultimul commit|
|ștergi modificările locale|`git checkout -- <fisier>`|versiunea din ultimul commit|

---

# 🧰 **Nivel 5 – GitIgnore & GitKeep**

👉 scop: să controlezi ce intră în repo.

|Scop|Comandă / fișier|Explicație|
|---|---|---|
|creezi fișier de ignorare|`.gitignore`|definește ce fișiere să nu urce|
|verifici ce e ignorat|`git status --ignored`|vezi și cele ignorate|
|păstrezi folder gol|`.gitkeep`|fișier placeholder într-un folder gol|

---

# 💬 **Nivel 6 – Pull/Merge Requests în GitLab**

👉 nu e comandă Git, dar e fluxul de lucru tipic DevOps.

1. `git push origin topic`
    
2. În GitLab → **Merge Requests → New MR**
    
3. Alege `source = topic`, `target = main`
    
4. Verifică dif-urile, apasă “Merge”
    
5. (Opțional) șterge branch-ul după merge
    

---

# 🧠 **Nivel 7 – Comenzi avansate și utile**

|Scop|Comandă|Explicație|
|---|---|---|
|vezi ultimele commituri scurte|`git log --oneline`|rapid|
|vezi diferențele locale|`git diff`|ce s-a schimbat|
|vezi autorul liniilor|`git blame <fisier>`|cine a modificat fiecare linie|
|vezi cine a schimbat ce fișiere|`git shortlog -sn`|statistici pe user|
|creezi un tag|`git tag v1.0`|versiune fixă|
|împingi tag-urile|`git push --tags`|urcă toate tag-urile|