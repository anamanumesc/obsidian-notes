connects MAC + IP ADRESSES
mac - network card identifier


mac = network interface card


### 🔹 Cum funcționează ARP (super important)

Când laptopul vrea să trimită ceva la o adresă IP din rețeaua sa locală (ex: 192.168.0.20):

1. Se uită în **ARP cache-ul** local:
    
    - „Am eu deja adresa MAC (fizică) asociată IP-ului 192.168.0.20?”
        
    - Dacă DA → o folosește direct.
        
2. Dacă NU → trimite un **ARP broadcast**:
    
    > „Cine are IP-ul 192.168.0.20? Spune-mi adresa ta MAC!”
    
3. Imprimanta răspunde:
    
    > „Eu am IP-ul 192.168.0.20, adresa mea MAC e AA:BB:CC:DD:EE:FF.”
    
4. Laptopul salvează asta în cache-ul ARP și trimite datele direct la imprimantă (prin switch sau Wi-Fi).
    

💡 Totul se întâmplă **fără router** — doar la nivelul rețelei locale (Layer 2 – Ethernet).