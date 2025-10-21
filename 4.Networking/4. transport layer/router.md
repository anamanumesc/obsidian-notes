
### 🔸 Fluxul intern în router:

1. **Laptopul tău trimite un pachet** (ex: către Internet).
    
2. Routerul îl primește pe interfața LAN.
    
3. Routerul analizează:
    
    - Destinația e în LAN-ul meu? (adică același subnet)
        
        - ✅ DA → trimite direct (fără NAT, fără firewall)
            
        - ❌ NU → merge la procesul de rutare.
            
4. Dacă merge la rutare:
    
    - verifică **tabela de rutare** (unde să trimit pachetul)
        
    - aplică regulile de **firewall** (poate bloca sau permite)
        
    - dacă destinația e Internet → aplică **NAT**
        
5. Apoi îl trimite prin interfața WAN spre ISP.
    

🧠 Firewall-ul **nu e un dispozitiv separat** între router și gateway.  
El e **un modul software în router**, care se aplică **înainte** ca pachetul să iasă.



router 
Routers sit _between_ networks.  
That means they have **at least two IP addresses**:

1. **Private-side (LAN)** → example `192.168.1.1`

    - This connects to your local home network 
    - It shares the first three octets (`192.168.1`) with your devices.
    - Your phone/laptop use it as the **gateway**
    
2. **Public-side (WAN)** → example `81.23.45.6`

    - This connects to your ISP and the Internet. 
    - It’s completely different from the private network.



When you go online, your router uses **NAT (Network Address Translation)** to make all your devices appear as **one public IP**.



## 🧭 2. Routerul are **două adrese IP**

Exact cum ai zis 💡 — routerul este „punctul de legătură” între **rețeaua ta privată (LAN)** și **Internetul public (WAN)**.

|Interfață|Exemplu IP|Rol|
|---|---|---|
|**Privată (LAN)**|192.168.0.1|Folosită pentru a comunica cu dispozitivele tale locale (PC, telefon, TV)|
|**Publică (WAN)**|82.137.44.5|Folosită pentru a comunica cu Internetul (vizibilă de servere externe)|





