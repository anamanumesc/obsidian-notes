📚 Ghid Specific: Ce Am Făcut Noi Împreună în Acest Proiect
🔍 PARTEA 1: Problema Inițială - De Ce Nu Se Afișau Cărțile?
1.1 Diagnosticarea Problemei
De ce când accesam http://localhost:8080/ nu vedeam nicio carte?
Ce înseamnă eroarea "Invalid object name 'Users'" pe care am primit-o?
De ce backend-ul răspundea cu {"ok":true} dar frontend-ul nu afișa date?
Ce era problema cu 304 Not Modified și cache-ul browser-ului?
1.2 Prima Verificare - Backend vs Frontend
Cum am verificat că backend-ul rulează pe portul 4000?
De ce API-ul returna cărți când îl testam cu curl dar nu în browser?
Ce diferență era între portul 3000 și 4000 în configurații?
Cum am descoperit că există o carte "Ion" de Liviu Rebreanu în baza de date?
🛢️ PARTEA 2: Crearea Schemei Bazei de Date
2.1 De la Controllers la Schema
Cum am analizat fișierele authController.js, bookController.js, exchangeController.js?
Ce tabele am identificat că trebuie să existe: Users, Books, Exchanges, BookHistory?
De ce am avut nevoie să citesc codul pentru a înțelege structura bazei de date?
Cum am generat schema.sql bazat pe logica din controllers?
2.2 Problemele cu Crearea Tabelelor
De ce am primit eroarea "CREATE TRIGGER must be the first statement in a query batch"?
Ce sunt statement-urile GO și de ce le-am adăugat în schema.sql?
De ce am avut conflict cu "FK_BookHistory_User" și cascade delete cycles?
Cum am rezolvat problema prin eliminarea ON DELETE CASCADE?
2.3 Executarea Schemei în Container
De ce am folosit docker cp schema.sql mssql:/tmp/schema.sql?
Cum am executat schema-ul cu sqlcmd în containerul SQL Server?
De ce am făcut DROP TABLE IF EXISTS înainte să recreez tabelele?
Cum am verificat că toate cele 4 tabele s-au creat corect?
🔧 PARTEA 3: Problema Configurărilor API
3.1 Inconsistențele de URL-uri
De ce aveam http://localhost:3000/api în auth.js și 4000 în main.js?
Ce era problema cu process.env.VUE_APP_API_URL din api.js?
De ce backend-ul răspundea pe portul 4000 dar frontend-ul căuta pe 3000?
Cum am identificat că toate trei serviciile (auth.js, api.js, main.js) trebuie să pointeze la 4000?
3.2 Repararea Configurărilor
Ce fișiere am modificat pentru a repara URL-urile API?
De ce am schimbat const API_URL = 'http://localhost:3000/api' în 4000?
Cum am înlocuit process.env.VUE_APP_API_URL cu o valoare hardcoded?
De ce nu am setat environment variable în loc să hardcode-z URL-ul?
🐳 PARTEA 4: Problemele cu Containerele
4.1 Frontend Container și Cache
De ce după modificări frontend-ul păstra versiunea veche?
Ce înseamnă că frontend-ul folosea serve -s dist (versiunea built)?
De ce docker-compose restart frontend nu era suficient?
Cum am forțat rebuild-ul cu docker-compose build frontend?
4.2 Containerul în Modul Development vs Production
Care e diferența între npm run serve (development) și serve -s dist (production)?
De ce containerul nostru folosește versiunea built și nu development?
Cum am verificat hash-ul JavaScript bundle-ului (app.523c9219.js vs app.262fe1c0.js)?
De ce am folosit docker-compose stop frontend && docker-compose rm -f frontend?
🔑 PARTEA 5: Problema JWT_SECRET
5.1 Descoperirea Problemei
De ce înregistrarea utilizatorului returna "Server error"?
Ce eroare am văzut în logs: "secretOrPrivateKey must have a value"?
Cum am verificat că JWT_SECRET lipsea cu docker exec backend printenv | grep JWT?
De ce autentificarea nu putea să genereze token-uri fără JWT_SECRET?
5.2 Rezolvarea în Docker-Compose
Unde am adăugat JWT_SECRET în docker-compose.yml?
Ce valoare am pus: "your-super-secret-jwt-key-change-in-production"?
De ce am adăugat și CORS_ORIGIN în environment variables?
Cum am avut problema cu duplicatul "CORS_ORIGIN" și am reparat-o?
5.3 Restart-ul Backend-ului
De ce docker-compose restart backend nu a încărcat environment variables?
Cum am forțat recrearea containerului cu stop && rm -f && up -d?
Cum am verificat că JWT_SECRET s-a setat corect după restart?
De ce am testat înregistrarea cu curl și test-user.json?
🔄 PARTEA 6: Debugging și Logging
6.1 Adăugarea de Console.log
De ce am adăugat logging în HomePage.vue și api.js?
Ce console.log-uri am pus: "HomePage: Fetching books with filters:" și "API: Response received:"?
Cum am rebuild containerul frontend după adăugarea debug-ului?
De ce debug-ul ne ajută să vedem exact unde se oprește flow-ul de date?
6.2 Testarea Manuală
Cum am testat API-ul direct cu curl 'http://localhost:4000/api/books/filtered'?
De ce am verificat CORS cu header-ul Origin: http://localhost:8080?
Cum am creat fișierul test-api.html pentru a testa în browser?
Ce comenzi am folosit pentru a verifica statusul containerelor?
🧪 PARTEA 7: Testarea Finală a Sistemului
7.1 Verificarea Tuturor Serviciilor
Cum am verificat că toate 3 containerele (db, backend, frontend) rulează?
Ce endpoint-uri am testat: /api/health, /api/books/filtered, /api/books/filter-options?
Cum am verificat datele din baza de date cu sqlcmd?
Ce am găsit: 1 user, 1 carte, 0 exchange requests?
7.2 Testarea Funcționalității Complete
Cum am testat înregistrarea unui utilizator nou cu API-ul?
Ce JSON am folosit în test-user.json?
De ce primul test a eșuat și al doilea a reușit?
Cum am verificat că token-ul JWT se generează corect?
🎯 PARTEA 8: Soluția Finală
8.1 Ce am Reparat Exact
Lista completă: schema bazei de date, URL-uri API, JWT_SECRET, rebuild frontend?
În ce ordine am rezolvat problemele și de ce în ordinea aceea?
Ce fișiere am modificat: auth.js, api.js, schema.sql, docker-compose.yml?
Cum am verificat că fiecare fix funcționează înainte să trec la următorul?
8.2 Rezultatul Final
De ce acum cartea "Ion" se afișează pe http://localhost:8080?
Cum am confirmat că frontend-ul primește datele de la backend?
Ce înseamnă că toate containerele sunt "healthy" sau "running"?
Cum știu că sistemul este complet funcțional pentru development?
🔍 PARTEA 9: Lecțiile Învățate
9.1 Probleme Comune în Docker Development
De ce cache-ul browser-ului poate să ne păcălească în development?
Cum identificăm când trebuie să rebuild-uim containers vs restart?
De ce environment variables trebuie să fie setate corect de la început?
Cum debug-uim probleme de comunicare între containere?
9.2 Best Practices Descoperite
De ce toate URL-urile API trebuie să fie consistente în tot frontend-ul?
Cum verificăm că schema bazei de date match-uie cu codul backend-ului?
De ce logging-ul și console.log-urile sunt esențiale pentru debugging?
Cum testăm fiecare serviciu independent înainte să testăm integrarea?
🎯 Aceste întrebări acoperă exact workflow-ul pe care l-am parcurs împreună - de la problema inițială (cărțile nu se afișau) până la soluția completă (sistem funcțional). Fiecare întrebare se bazează pe ceva concret pe care l-am făcut sau reparat în această conversație!

