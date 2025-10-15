
1. Install _Apache/nginx_ 
2. Deploy a "hello world" page, expose it and access it from the browser
3. Check the logs of the system and webserver

```bash
# 1) Instalează și pornește Nginx (serviciu web)
sudo apt update
sudo apt install -y nginx
sudo systemctl enable --now nginx
# -> pornește și pune Nginx să pornească automat la boot

# 2) Pune pagina „Hello World” în document root (implicit: /var/www/html)
echo '<h1>Hello, world!</h1>' | sudo tee /var/www/html/index.html > /dev/null
# -> acum Nginx va servi acest fișier ca răspuns pentru http://IP/

# 3) (Dacă ai UFW) deschide porturile HTTP/HTTPS
sudo ufw allow 'Nginx Full'
# -> permite traficul către 80 (HTTP) și 443 (HTTPS)

# 4) Verifică că Nginx ascultă pe 80 și că pagina răspunde local
sudo netstat -ltnp | grep ':80'
         # vezi că ascultă pe 0.0.0.0:80
curl http://localhost/         # ar trebui să vezi conținutul "Hello, world!"

# 5) Află IP-ul pentru a deschide din browser (de pe alt device în aceeași rețea)
hostname -I | awk '{print $1}'
# -> în browser: http://<IP-ul_afisat>/

```

Logs

```bash
# Cereri (cine a accesat, ce URL, cod status)
sudo tail -f /var/log/nginx/access.log
# ex: 192.168.1.10 "GET / HTTP/1.1" 200 ...

# Erori (fișiere lipsă, permisiuni, probleme config)
sudo tail -f /var/log/nginx/error.log

# Jurnalul serviciului (porniri, reload)
sudo journalctl -u nginx -f

```

daca aveam mai multe fisiere unde le puneam?



1. pe ce ip este afisat atunci # 5) Află IP-ul pentru a deschide din browser (de pe alt device în aceeași rețea) hostname -I | awk '{print $1}'-> în browser: http://<IP-ul_afisat>/ ?
2. ip-ul public sau privat al masinii virtuale sau al masinii host? 
3. cum functioneaza ca ngnix sa astepre requesturi? gen cum le "Asculta ma rog"
4. de unde stie browserul unde sa trimita requestul
5. tema imi cere sa deschid in browser dar nu stiu daca se refera la browserul din vm sau din host.
6. firewall-ul exista in browser sau in laptop? cum functioneaza ad block-ul?
7. daca vreau ca eu sa pot sa  accesez din browser de pe localhost ce trebuie sa fac
8. daca vreau sa accesez de pe broswer de pe host amchien ce trebuie sa fac?
9. daca vreau sa accesez din lan ce trebuie sa fac?
10. daca rveau sa accesez de pe internet ce trebuie sa fac??
11. ajunge doar sa imi dau share la ip? si apoi browserul cu ip0ul si portul acceseaza ce are nevoie?
12.  -> permite traficul către 80 (HTTP) și 443 (HTTPS). ce inseamna catre? cuma dica deschid un port?
13. ngnix porneste un proces sau un 
14. ce sunt procesele daemon? cine le porneste? 
15. care e diferenta intradevar intre servicii si procese si socketuri?
16. 1. VM-ul are de obicei **IP privat**, de exemplu `192.168.1.10`.
    Când VM-ul vrea să acceseze internetul:
    
    - VM → router → NAT → internet.
        
    - NAT (Network Address Translation) schimbă IP-ul sursă din IP privat → IP public al router-ului.
        Serverul extern de pe internet răspunde → pachetele ajung la IP-ul public al router-ului → NAT înlocuiește IP-ul destinație cu IP-ul privat → VM primește răspunsul.
**Exemplu concret:**

- VM trimite cerere către `example.com`.
    
- Router-ul înlocuiește IP-ul sursă cu IP public: `203.0.113.25`.
    
- Serverul `example.com` trimite răspuns → router → VM.
ce nu inteleg eu e asta: deci nat schimba din ip privat al vm ului cu ipul public al hostului? dar eu credeam ca el ramane privat pana ajunge in ruter. si din ruter se tranforma in ip public. nu asa functioneaza? ipul din privat devine public cand ajunge in ruterula al de l avem in casa

17. atunci cand fac o cerere de pe browser de pe host oe