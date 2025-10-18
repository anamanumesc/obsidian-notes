1. do homework
2. watch courses
3. study those terms





4. deci cum se folosesc ip private si publice. mai ales in cazul meu aici
5. ce e socket bonding asta

6. pai nu ai zis tu ca eu pot sa accesez din browserul hostului, serverul vm-ului doar daca fac port binding? tu ai zis si acum zici asta : - - Browser pe host → trebuie să folosești **IP-ul privat al VM** și firewall-ul să permită accesul.
        
7. Important: host-ul trebuie să poată “vedea” VM-ul în rețea (network bridge sau NAT configurat).
8. ce inseamna sa asculti pe asta? - Nginx ascultă deja pe `0.0.0.0:80`.
9. cum functioneaza aceasta comunicare intre vm si internet. gen care e regula. cum circula informastia de pe internet pe vm si inapoi
10. ce inseamna asta: - Trebuie port forwarding pe router: port 80 → IP server.
11. deci eu daca vreau sa accesez internetul am nevoie neaparat de un ip public. cum se face aceasta tranzactie
12. ce sunt procesele daemon. si de ce unele sunt daemon unele nu. daca eru pot sa incep si procese normale dar si procese daemon.. care e sensul
13. dar nu asa sta cazul si cand vreau ca cineva sa acceseze un device? de ce trebuie neaparat pt vm acest port forwarwing? Pentru ca cineva de pe internet să ajungă la VM: router-ul trebuie să facă NAT/port forwarding de la IP public → IP privat.
14. deci eu in casa mea folosesc ip privat dar cand vreau sa parasesc office-ul sau building-ul atunci ruterul imi ofera un ip public? deci ip-ul public unde e? in router/
15. dar nu asa sta cazul si cand vreau ca cineva sa acceseze un device? de ce trebuie neaparat pt vm acest port forwarwing? Pentru ca cineva de pe internet să ajungă la VM: router-ul trebuie să facă NAT/port forwarding de la IP public → IP privat.
16. da dar eu cand am rulat ngpix pe vm si am vrut sa l accesez de pe host  nu mi a mers decat daca am facut port boinding: Nu e nevoie să ai port forwarding pentru LAN; port forwarding e necesar doar dacă vrei acces din internet.. eu cred ca confund port bonding cu port forwarding. ajuta ma sa inteleg la ce ma refer
17. sa asculti pe 0.0.0. inseamna ca asculti toate cererile TOATE? DE ORIUNDE? cum, adica. si lcoal host sit top
18. Poți porni orice proces ca daemon folosind `&` sau `systemd`. ok dar ce avantaje au aceste procese ce scop au si cum functioneaza


