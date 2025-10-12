

Tu ai o **placă de rețea virtuală**,  
→ pe care alegi un **tip de adaptor de rețea** (ex: NAT sau Host-Only),  
→ iar acel adaptor o conectează la o **rețea virtuală** creată de VirtualBox,  
→ care este văzută în Ubuntu ca o **interfață de rețea** cu propriul IP.



why cant virtualbox vm and wsl coexist
- they use the same hardware virtualization -> a processor feature called HYPERVISOR
- it uses Microsoft Hyper-V

NAT
- nat = *Network Address Translation*
- definitie: e un algritm/mecanism/proces care traduce adresele IP in VM
- pc-ul acceseaza vm-ul printr un IP privat
- acesta are un ip private
- vm ul poate sa acceseze 
- nat ii ofera un access iesire spre internet, nu intrare din exterior
- host only adapter - int
- placa de retea a vm-ului o setezi pe NAT
- foloseste deci internetul laptopului
- vm-ul are o adresa de ip privata care nu e cunoscuta inafara vm-ului
- nat schimba din aceasta adresa ip privata o schimba in adresa 

placa de retea
- network interface card (NIC) componenta fizica
- face legatura dintre router si SO
- trimitele pachetele de date in retea
- in cazul cand nu am o masina virtuala, NAT-ul se face direct in router

SSH
- ssh = SECURE SHELL - secure terminal
- fucntioneaza pe baza de cheie privata si publica
- e un **protocol** care permite sa te conectezi de la un calculator la altul printr o retea in moc securizat
- adica criptat
- creezi o cheie ssh pe laptop
- iar pe VM pui o cheie publica
- terminalul de pe laptop devine terminalul VM-ului
- te conectezi la un server sau la un VM
- host = masina ta
1. generezi o pereche de chei pe host
2. cheia publica o pui pe vm (o copiezi o pui acolo in /.ssh/authorized keys)
3. host-ul dechide terminalul si trimite un mesaj criptat
4. host-ul decripteaza cu cheia privata si verifica daca e ok si se conect


Host-only adapter
- private between computer and vm
- concept

ping
- verfici daca un server/vm e online. 
- trimiti un pachet special, un ecmp request

firewall



cum am facut
- din setarile masinii virtuale 
- a trebuit sa dau enable network adapter
- sa il atasez to host only adapter


apoi
- din ubuntu afisez interfetele de retea cu comanda ip adrr
- ca sa activez reteaua host only
- in fisierul NETPLAN decid ceca vreay sa folosesc o abumita adfresa ip




1. AM CONFIGURAT DOUA ADAPTOARE DE RETEA. UNUL HOST ONLY ADAPTER
2. AM SETAT UN IP STATIC PRIN FISIERUL DE NETPLAN
3. AM INSTALAT SI ACTIVAT SERVICIUL DE SSH PE UBUNTU, CA SA ACCESEZE COENEXIUNI EXTERNE
4. AM GENERAT CHEILE
5. M AM CONECTAT LA VM PRIN SSH



## 🧩 Cum se leagă toate între ele

1. **Placa de rețea virtuală (vNIC)**  
    → este „dispozitivul” virtual instalat în mașina ta virtuală (Ubuntu).  
    Ea există _în interiorul_ VM-ului și este echivalentul plăcii fizice dintr-un laptop real.
    
    💬 Poți avea mai multe plăci virtuale — fiecare conectată la un adaptor diferit.  
    Ex:
    
    - `enp0s3` → prima placă virtuală (pentru Internet prin NAT)
        
    - `enp0s8` → a doua placă virtuală (pentru rețea privată Host-Only)
        

---

2. **Adaptorul de rețea (Network Adapter – setarea din VirtualBox)**  
    → este _setarea_ care spune **cum** acea placă virtuală comunică cu lumea din afară.  
    El „leagă” placa ta virtuală de un anumit tip de rețea virtuală creată de VirtualBox.
    
    🔹 Poate fi de mai multe tipuri:
    
    - **NAT** – pentru acces la Internet prin gazdă (Windows)
        
    - **Host-Only** – pentru rețea locală între gazdă și VM
        
    - **Bridged** – pentru a face VM-ul să apară în aceeași rețea cu laptopul
        
    - **Internal** – pentru rețea doar între VM-uri
        

---

3. **Rețeaua virtuală locală (creată de adaptor)**  
    → este spațiul logic de comunicare creat automat de VirtualBox, unde IP-urile funcționează.  
    De exemplu:
    
    - „vboxnet0” este rețeaua Host-Only între Windows și Ubuntu (`192.168.56.x`)
        
    - NAT are propria rețea internă (ex: `10.0.2.x`)
        

---

4. **Interfața de rețea (în sistemul Ubuntu)**  
    → este partea software care controlează acea placă virtuală și are IP-ul asociat.  
    De exemplu:
    
    - `enp0s3` (pentru NAT, IP 10.0.2.15)
        
    - `enp0s8` (pentru Host-Only, IP 192.168.56.101)
        

---

## 🔁 Imagine logică simplă

- 🧱 **Placa virtuală** = componenta instalată în VM (hardware-ul virtual)
    
- ⚙️ **Adaptorul de rețea** = setarea care o leagă la un tip de rețea (NAT, Host-Only etc.)
    
- 🌐 **Rețeaua virtuală locală** = „drumul” pe care circulă datele între mașini
    
- 💻 **Interfața de rețea** = controlul software și IP-ul din sistemul de operare