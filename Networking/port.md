 ### De ce avem nevoie de porturi

- O mașină rulează mai multe servicii simultan.
    
- Fără porturi, serverul nu ar ști **că cererea HTTP trebuie la Nginx și nu la MySQL**.



## **3️Cum funcționează în rețea**

1. Browser/SSH/etc. trimite un pachet către **IP + port**.
    
2. Kernel-ul mașinii ținte verifică portul: cine “ascultă” pe portul ăla?
    
3. Dacă există un proces care ascultă (`listen socket`) → pachetul merge acolo.



ip - adresa casei
port - camera

oate avea stari:

listen - asteapta coneciuni noi
established
time wait - recent inchisa


8000-9000 neprivileiate, nu necesita root
nu sunt folosite de servicii critice