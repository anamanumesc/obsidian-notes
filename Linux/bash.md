```bash
# 🧠 Bash Scripting Cheatsheet

## 1️⃣ Structura de bază a unui script
#!/bin/bash
# Comentariu - explică ce face scriptul
echo "Salut lume!"   # afișează text

# Cum rulezi:
chmod +x script.sh   # dă permisiune de execuție
./script.sh


## 2️⃣ Variabile
nume="Maria"
echo "Salut, $nume"

# Note:
# - Nu pui spații în jurul semnului '='
# - Variabilele se folosesc cu $ (ex: $nume)


## 3️⃣ Citirea inputului
read -p "Introdu numele tău: " nume
echo "Salut, $nume!"


## 4️⃣ Condiții IF
if [ $x -gt 10 ]; then
    echo "Mai mare ca 10"
elif [ $x -eq 10 ]; then
    echo "E egal cu 10"
else
    echo "Mai mic ca 10"
fi

# Operatori utili:
# -eq   egal
# -ne   diferit
# -lt   mai mic
# -le   mai mic sau egal
# -gt   mai mare
# -ge   mai mare sau egal


## 5️⃣ Buclă FOR
for i in 1 2 3 4 5; do
    echo "Număr: $i"
done

# Alt exemplu:
for file in *.txt; do
    echo "Fișier: $file"
done


## 6️⃣ Buclă WHILE
count=1
while [ $count -le 5 ]; do
    echo "Iterația $count"
    ((count++))
done


## 7️⃣ Funcții
function salut() {
    echo "Salut, $1!"
}

salut "Maria"   # apelează funcția
# $1, $2, ... sunt argumentele funcției


## 8️⃣ Argumente la script
#!/bin/bash
echo "Primul argument: $1"
echo "Toate argumentele: $@"
echo "Număr de argumente: $#"

# Rulare:
# ./script.sh unu doi trei


## 9️⃣ Comenzi utile
# pwd            -> afișează calea curentă
# ls             -> listează fișierele
# cd dir         -> schimbă directorul
# mkdir dir      -> creează un director
# rm file        -> șterge un fișier
# cat file       -> afișează conținutul
# grep "text" file   -> caută text în fișier
# chmod +x file      -> face fișierul executabil


## 🔟 Substituție de comenzi
data=$(date)
echo "Astăzi este: $data"


## 💡 Trucuri rapide
mkdir test && cd test       # execută a doua doar dacă prima reușește
cd folder || echo "Folderul nu există"   # execută a doua dacă prima eșuează
echo "1"; echo "2"          # execută ambele comenzi indiferent


## 🧩 Verifică dacă fișierul există
if [ -f "fisier.txt" ]; then
    echo "Fișierul există."
else
    echo "Nu există fișierul."
fi


## 🔧 Shortcut-uri utile în terminal
# Ctrl + C  -> oprește execuția
# Ctrl + L  -> curăță ecranul
# !!        -> repetă ultima comandă
# ↑ / ↓     -> navighează prin istoric
# Tab       -> autocomplete
```
