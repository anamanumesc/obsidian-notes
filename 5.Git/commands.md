# Fundamentale

| Scop                                  | Comandă                                      | Explicație scurtă                               |
| ------------------------------------- | -------------------------------------------- | ----------------------------------------------- |
| inițializează un repo local           | `git init`                                   | creează folderul `.git`                         |
| clonează un repo existent             | `git clone <url>`                            | ia o copie locală a unui repo GitLab/GitHub     |
| verifică statusul                     | `git status`                                 | vezi fișiere modificate, staged, untracked      |
| adaugă fișiere în staging             | `git add <fisier>`                           | pregătește fișierul pentru commit               |
| adaugă tot                            | `git add .`                                  | adaugă toate modificările curente               |
| creează un commit                     | `git commit -m "mesaj"`                      | salvează snapshot-ul în istoric                 |
| vezi istoricul                        | `git log`                                    | lista completă de commit-uri                    |
| vezi pe scurt istoricul               | `git log --oneline --graph --decorate --all` | grafic simplificat cu ramuri                    |
| anulează modificările dintr-un fișier | `git restore <fisier>`                       | revine la ultima versiune salvată               |
| scoate fișiere din staging            | `git restore --staged <fisier>`              | le lasă modificate, dar nelistate pentru commit |

---

# Lucrul cu remote (GitLab)

|Scop|Comandă|Explicație|
|---|---|---|
|adaugă remote|`git remote add origin <url>`|conectează repo local la GitLab|
|vezi remote-urile|`git remote -v`|verifică legătura cu GitLab|
|trimiți schimbările prima dată|`git push -u origin main`|setează legătura locală–remote|
|trimiți schimbările următoare|`git push`|după ce upstream e setat|
|aduci modificări din remote|`git pull`|actualizează localul cu ce e pe GitLab|
|descarcă fără a fuziona|`git fetch`|doar aduce, nu schimbă localul|
|sincronizează complet|`git pull origin main --allow-unrelated-histories`|utile la repo-uri divergente|

---

# Branching și Merging

|Scop|Comandă|Explicație|
|---|---|---|
|creează o ramură nouă|`git branch topic`|doar creează branch local|
|comută pe alt branch|`git checkout topic`|te mută pe acel branch|
|creează și comută direct|`git checkout -b topic`|scurtătură comună|
|vezi ramurile existente|`git branch -a`|arată ramuri locale și remote|
|vezi ramurile locale cu tracking|`git branch -vv`|arată ce remote urmărește fiecare|
|unește topic în main (fast-forward)|`git merge --ff-only topic`|mută pointerul main înainte fără commit de merge (doar dacă main nu are commituri noi)|
|unește topic în main (merge normal)|`git merge topic`|creează automat merge commit dacă e nevoie|
|unește cu commit explicit (no fast-forward)|`git merge --no-ff topic`|forțează commit de merge chiar dacă se putea fast-forward|
|rezolvă conflicte manual|`git add <fisier>` + `git commit`|după editarea fișierelor marcate conflictuate|
|vezi diferențe între branch-uri|`git diff main..topic`|arată modificările dintre două ramuri|
|șterge o ramură locală|`git branch -d topic`|șterge dacă e deja îmbinată|
|șterge forțat o ramură|`git branch -D topic`|șterge indiferent de stare|
|trimite o ramură la remote|`git push -u origin topic`|creează branch-ul și pe GitLab|
|șterge o ramură de pe remote|`git push origin --delete topic`|elimină branch-ul remote|

---

# Rebase, Reset, Restore (manipularea istoricului)

|Scop|Comandă|Explicație|
|---|---|---|
|aduci main în topic|`git rebase main`|aplică commit-urile din topic peste main|
|continui rebase după conflict|`git rebase --continue`|după rezolvarea conflictelor|
|anulezi rebase-ul|`git rebase --abort`|revii la starea dinainte|
|rescrii istoricul local complet|`git reset --hard origin/main`|aliniază 100% la remote|
|muți HEAD cu un commit înapoi|`git reset HEAD~1`|anulează ultimul commit (păstrează modificările)|
|ștergi modificările locale complet|`git checkout -- <fisier>`|revine la ultima versiune comisă|

---

# GitIgnore & GitKeep

|Scop|Comandă / fișier|Explicație|
|---|---|---|
|creezi fișierul `.gitignore`|`.gitignore`|definește fișierele/directoarele ignorate|
|verifici ce e ignorat|`git status --ignored`|afișează și fișierele excluse|
|verifici regula care ignoră ceva|`git check-ignore -v <fisier>`|arată regula exactă și fișierul .gitignore|
|scoți fișiere deja urcate, dar acum ignorate|`git rm --cached <fisier>`|le șterge doar din index, nu de pe disc|
|păstrezi un folder gol|`.gitkeep`|fișier placeholder pentru directoare goale|
|comiți folderul gol|`git add Folder1/.gitkeep`|face vizibil folderul gol pe remote|

---

# Pull/Merge Requests în GitLab

1. `git push origin topic`
    
2. În GitLab → **Merge Requests → New MR**
    
3. Alege `source = topic`, `target = main`
    
4. Verifică dif-urile și apasă **Merge**
    
5. (Opțional) șterge branch-ul `topic` după merge
    

---

# Comenzi avansate și utile

| Scop                                    | Comandă                         | Explicație                                 |
| --------------------------------------- | ------------------------------- | ------------------------------------------ |
| vezi ultimele commit-uri concise        | `git log --oneline`             | afișare scurtă, o linie per commit         |
| vezi diferențele locale                 | `git diff`                      | arată ce s-a schimbat în fișiere           |
| vezi diferențele staged                 | `git diff --staged`             | compară staging cu ultimul commit          |
| vezi cine a modificat fiecare linie     | `git blame <fisier>`            | arată autorul fiecărei linii               |
| vezi cine a comis câte fișiere          | `git shortlog -sn`              | statistici per utilizator                  |
| creezi un tag nou                       | `git tag v1.0`                  | etichetează o versiune                     |
| împingi tag-urile la remote             | `git push --tags`               | trimite toate tag-urile definite           |
| vezi remote branch-urile                | `git ls-remote --heads origin`  | listează ramurile disponibile pe remote    |
| arată conținutul unui fișier din remote | `git show origin/main:<fisier>` | utile pentru verificarea stării remote     |
| afișează locația repo-ului              | `git rev-parse --show-toplevel` | arată calea absolută a rădăcinii repo-ului |






----



| #   | 🔹 Scop / Pas                                                   | 🐧 **Ubuntu (Terminal / Bash)**                                                                                   | 🪟 **Windows PowerShell (Admin)**                                                                                                                                       |
| --- | --------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | 🔍 Vezi interfețele și IP-urile actuale                         | `ip a`                                                                                                            | `Get-NetIPConfiguration`                                                                                                                                                |
| 2   | 🔧 Identifică adaptorul Host-Only (ex: `enp0s8` / `Ethernet 2`) | `nmcli device status` sau `ip a`                                                                                  | `Get-NetAdapter`                                                                                                                                                        |
| 3   | ⚙️ Dezactivează DHCP și setează IP static                       | `bash\nsudo ip addr flush dev enp0s8\nsudo ip addr add 192.168.56.12/24 dev enp0s8\nsudo ip link set enp0s8 up\n` | `powershell\nSet-NetIPInterface -InterfaceAlias "Ethernet 2" -Dhcp Disabled\nNew-NetIPAddress -InterfaceAlias "Ethernet 2" -IPAddress 192.168.56.10 -PrefixLength 24\n` |
| 4   | 🧱 Verifică IP-ul configurat                                    | `ip a show enp0s8`                                                                                                | `Get-NetIPAddress -InterfaceAlias "Ethernet 2"`                                                                                                                         |
| 5   | 🔎 Verifică regulile firewall-ului (dacă permite ICMP / ping)   | `sudo ufw status verbose`                                                                                         | ```powershell\nGet-NetFirewallRule```                                                                                                                                   |
| 6   | 🔥 Permite ping (ICMP) prin firewall                            | `sudo ufw allow proto icmp` _(sau)_ `sudo ufw disable`                                                            | `netsh advfirewall firewall set rule group="File and Printer Sharing" new enable=yes`                                                                                   |
| 7   | 🧾 Setează hostname permanent                                   | `sudo hostnamectl set-hostname vm-ubuntu-1`                                                                       | `Rename-Computer -NewName 'vm-windows-1' -Force`                                                                                                                        |
| 8   | 💾 Repornește pentru aplicarea hostname-ului                    | `sudo reboot`                                                                                                     | `Restart-Computer`                                                                                                                                                      |
| 9   | 🧩 Adaugă în fișierul _hosts_ pentru rezoluție locală           | ```bash\necho "192.168.56.10 vm-windows-1"                                                                        | sudo tee -a /etc/hosts\necho "192.168.56.12 vm-ubuntu-1"                                                                                                                |
| 10  | 🔄 Golește cache DNS (după modificări hosts)                    | `sudo systemd-resolve --flush-caches`                                                                             | `ipconfig /flushdns`                                                                                                                                                    |
| 11  | 🧪 Testează conexiunea între VM-uri                             | `ping 192.168.56.10` sau `ping vm-windows-1`                                                                      | `Test-Connection vm-ubuntu-1 -Count 2`                                                                                                                                  |
|     |                                                                 |                                                                                                                   |                                                                                                                                                                         |



ce am fcaut eu:
1. am creeat adaptorul host only ca sa fie totate in aceeasi retea interna locala
2. am facuit reteaua privata

ce s a intmplat dupa o perioada
1. s au reasignat alte ip-uri de la dhcp
2. reteaua s a schimbat automat de la privat la public. pt ca ip-urile s au schimbat reteaua nu era srtabila si windows a considerat ca e noua
3. nu mai puteam sa dau ping


ce trebuia sa fac diferit:  
1. trebuia sa setez ip-ul static, sa dezactivez dhcp
2. sa fca regulile de firewall sa fie permanente





![[Pasted image 20251026233137.png]]


Salut Radu! Am rezolvat problema cu virtualbox si acum merge mult mai bine si afiseaza mai mult de 3 cadre pe secunda 😄. Multumesc pentru sfaturi si materialele trimise!

Am analizat de ce nu functiona ping-ul intre masinile virtuale si am descoperit ca DHCP ul a reasignat automat alte adrese IP, iar Windows a identificat reteaua ca fiind una noua si a aplicat regulile implicite de firewall pentru retele publice, care sunt mai restrictive.

Ca sa nu mai am aceeasi problema in viitor, o sa am grija sa:

1.  setez adrese IP statice pentru adaptoarele host-only;
2. dezactivez DHCP-ul pentru acea retea, ca sa evit reasignarea automata a IP-urilor;
3. (si/sau) sa fac regulile de firewall permanente, astfel incat comunicarea sa nu fie afectata daca windows schimba profilul retelei.

Dupa ce am facut toti pasii, am testat si imi functioneaza chiar si dupa ce dau restart sau ma conectez la alta retea!