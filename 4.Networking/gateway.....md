
|                                                                                                         |
| ------------------------------------------------------------------------------------------------------- |
| A **device or IP address** on that network that knows how to forward packets _beyond_ the local subnet. |


- it has an ip address
- basically when u wanna reach smth outside of the LAN, you first reach the gateway. 
- in my house the gateway is the router
- a "a door between networks"
- a firewall or load balancer can take the role of a gateway
- ip 
- adress next-hop address the packets are sent to




“This destination is reachable **directly**, without needing a gateway.”
**On-link route** → destination is in the same subnet as one of your interfaces.




## 🧭 2. Routerul are **două adrese IP**

Exact cum ai zis 💡 — routerul este „punctul de legătură” între **rețeaua ta privată (LAN)** și **Internetul public (WAN)**.

| Interfață         | Exemplu IP  | Rol                                                                       |
| ----------------- | ----------- | ------------------------------------------------------------------------- |
| **Privată (LAN)** | 192.168.0.1 | Folosită pentru a comunica cu dispozitivele tale locale (PC, telefon, TV) |
| **Publică (WAN)** | 82.137.44.5 | Folosită pentru a comunica cu Internetul (vizibilă de servere externe)    |

➡️ **Laptopul folosește adresa privată a routerului (192.168.0.1) ca gateway.**  
Când vrei să accesezi Internetul, routerul:

1. primește pachetele de la tine,
    
2. le rescrie (NAT) cu **adresa publică**,
    
3. le trimite către Internet.