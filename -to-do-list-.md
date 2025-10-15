1. do homework from gitlab (two scripts)
2. do homeowrk from confluence (deploy the web)
3. study the homework!
4. study those terms
5. study the commands


understand the first and second script
understand how ngnix works- understand the second homework





PS C:\Users\bmaria> ssh -i "$env:USERPROFILE\.ssh\id_rsa_vm" remoteuser@192.168.56.101



1. deci cum se folosesc ip private si publice. mai ales in cazul meu aici
2. ce e socket bonding asta

3. pai nu ai zis tu ca eu pot sa accesez din browserul hostului, serverul vm-ului doar daca fac port binding? tu ai zis si acum zici asta : - - Browser pe host → trebuie să folosești **IP-ul privat al VM** și firewall-ul să permită accesul.
        
4. Important: host-ul trebuie să poată “vedea” VM-ul în rețea (network bridge sau NAT configurat).
5. ce inseamna sa asculti pe asta? - Nginx ascultă deja pe `0.0.0.0:80`.
6. cum functioneaza aceasta comunicare intre vm si internet. gen care e regula. cum circula informastia de pe internet pe vm si inapoi
7. ce inseamna asta: - Trebuie port forwarding pe router: port 80 → IP server.
8. deci eu daca vreau sa accesez internetul am nevoie neaparat de un ip public. cum se face aceasta tranzactie
9. ce sunt procesele daemon. si de ce unele sunt daemon unele nu. daca eru pot sa incep si procese normale dar si procese daemon.. care e sensul
10. dar nu asa sta cazul si cand vreau ca cineva sa acceseze un device? de ce trebuie neaparat pt vm acest port forwarwing? Pentru ca cineva de pe internet să ajungă la VM: router-ul trebuie să facă NAT/port forwarding de la IP public → IP privat.
11. deci eu in casa mea folosesc ip privat dar cand vreau sa parasesc office-ul sau building-ul atunci ruterul imi ofera un ip public? deci ip-ul public unde e? in router/
12. dar nu asa sta cazul si cand vreau ca cineva sa acceseze un device? de ce trebuie neaparat pt vm acest port forwarwing? Pentru ca cineva de pe internet să ajungă la VM: router-ul trebuie să facă NAT/port forwarding de la IP public → IP privat.
13. da dar eu cand am rulat ngpix pe vm si am vrut sa l accesez de pe host  nu mi a mers decat daca am facut port boinding: Nu e nevoie să ai port forwarding pentru LAN; port forwarding e necesar doar dacă vrei acces din internet.. eu cred ca confund port bonding cu port forwarding. ajuta ma sa inteleg la ce ma refer
14. sa asculti pe 0.0.0. inseamna ca asculti toate cererile TOATE? DE ORIUNDE? cum, adica. si lcoal host sit top
15. Poți porni orice proces ca daemon folosind `&` sau `systemd`. ok










---

pt jira:


adaug commuri 
adaug description si fac crosss


la proiecte nu modific description. doar adaug commuri noi