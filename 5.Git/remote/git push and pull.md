
1. origin = alias catre url unui server (git remote -v ca sa l vad)

2. git remote add origin https://github.com/user/proj.git
- ce face: ORIGIN devine acum alias pentru acel link

1. git push -u origin <branch_name>
- cand sunt pe acest branch si vr sa fac pull/push, folosesc link-ul din origin si numele branch-ului

1. git push 
- -u = --set-upstream
- seteaza legatura intre branch remote si branch local
- daca adaug -u nu trebuie sa adaug ce anume de fiecare data

1. `git fetch [origin]` Aduce **noutățile** de pe remote **fără** să le combine în branchul tău. Actualizează pointerii de tip `origin/main`, `origin/dev`. pai si eu daa vr sa ma uit in fetch cum fac asta???

