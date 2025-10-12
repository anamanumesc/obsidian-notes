## **1️⃣ Procesul de a face tema / pași practici**

- **Instalare Ubuntu VM** → izolare pentru laborator DevOps
    
- **Configurare rețea VM**
    
    - NAT activ by default → VM poate accesa internetul
        
    - Host-only → VM are IP privat accesibil din laptop (host)
        
- **SSH**
    
    - Generare cheie pe host (`ssh-keygen`)
        
    - Copierea cheii publice pe VM (`ssh-copy-id`)
        
    - Conectare SSH (`ssh user@IP_VM`)
        
- **Procedura**: boot VM → configurare rețea → test ping → creare chei → test SSH
    
- **Troubleshooting tipic**:
    
    - VM nu răspunde → verificat IP, NAT, host-only
        
    - SSH nu se conectează → verificat chei public/private, firewall
        

---

## **2️⃣ Probleme întâlnite**

- NAT-ul este pus by default → VM poate ieși pe internet fără alte setări
    
- IP-ul host-only poate să fie greșit sau VM-ul să nu fie pornit → ping eșuează
    
- SSH key necopiată corect → autentificare eșuează
    

---

## **3️⃣ Versiunea instalată**

- **Ubuntu 24.04.3 LTS** „Noble Numbat” → stabilă, LTS (5 ani suport)
    

---

## **4️⃣ Aplicația pentru azi**

- **Docker** → containerizare pentru aplicații
    
- Concept: codul aplicației se „împachetează” într-un container → poate rula pe orice mașină cu Docker
    
- Exemplu: proiect nou → cod → Dockerfile → `docker build` → `docker run`
    

---

## **5️⃣ Ce face DevOps**

- Integrează **dezvoltarea (Dev) și operațiunile (Ops)**
    
- Automatizare, monitorizare, livrare continuă
    
- Scalare aplicații și infrastructură
    
- Observabilitate și management performanță
    

---

## **6️⃣ Materiale de suport**

- Videoclipuri + prezentări:
    
    - `DevOps Intro.pptx`
        
    - „DevOps in 5 minutes”
        
    - „Making a difference with DevOps”
        
- Hands-on: configurare VM, rețea, SSH, Docker
    

---

## **7️⃣ Rezumat workflow temă**

1. Instalezi VM (Ubuntu 24.04 LTS)
    
2. Configurezi NAT + host-only
    
3. Creezi chei SSH → conectare la VM
    
4. Rulezi aplicație / proiect în Docker
    
5. Testezi conectivitate și funcționalitate
    
6. Documentezi pași, probleme întâlnite și soluții