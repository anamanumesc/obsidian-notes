
mai multe vlan-uri sunt in acelasi LAN

Nu poți avea **același subnet** pe VLAN-uri **diferite** — asta ar încurca rutarea.


## 🧩 1️⃣ Poți avea mai multe **subneturi** pe același **switch**?

✅ **DA, absolut.**  
Un singur switch fizic poate conține **mai multe subneturi**, dar fiecare subnet trebuie:

- să fie **asociat unui VLAN diferit**,
    
- și, dacă vrei ca ele să comunice între ele, ai nevoie de **un dispozitiv de Layer 3** (router sau Layer 3 switch).



