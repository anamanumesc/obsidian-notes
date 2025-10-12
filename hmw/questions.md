📚 Ghidul Complet pentru Înțelegerea Proiectului SchimbDeCartiRomania
🏗️ PARTEA 1: Arhitectura Generală a Proiectului
1.1 Concepte de Bază
Ce este o aplicație web și cum funcționează?
Ce înseamnă "frontend" și "backend" - analogia cu restaurantul?
Ce este o bază de date și de ce o folosim?
Ce înseamnă "client-server architecture"?
Cum comunică un browser cu un server?
1.2 Componentele Proiectului Nostru
Care sunt cele 3 părți principale ale proiectului nostru?
Ce face fiecare parte: Frontend (Vue.js), Backend (Node.js), Database (SQL Server)?
De ce avem nevoie de toate 3 părți?
Ce limbaje de programare folosim pentru fiecare parte?
🐳 PARTEA 2: Containerele Docker - Concepte Fundamentale
2.1 Ce sunt Containerele?
Ce este Docker și de ce îl folosim?
Ce este un "container" - analogia cu cutiile de transport?
Care este diferența între un container și o mașină virtuală?
Ce este o "imagine Docker" vs un "container"?
De ce containerele fac dezvoltarea mai ușoară?
2.2 Docker în Proiectul Nostru
Câte containere avem în proiectul nostru și care sunt ele?
Ce rulează în fiecare container?
De ce nu punem totul într-un singur container?
Ce este docker-compose și de ce îl folosim?
📁 PARTEA 3: Structura Fișierelor Docker
3.1 Fișierul docker-compose.yml
Ce este fișierul docker-compose.yml și ce face?
Ce înseamnă "services" în docker-compose?
Ce sunt "ports" și cum funcționează maparea porturilor?
Ce sunt "volumes" și de ce le folosim?
Ce sunt "environment variables" și cum le setăm?
3.2 Dockerfile-ul Frontend
Ce este un Dockerfile?
Cum se construiește imaginea frontend-ului?
Ce înseamnă "multi-stage build"?
De ce folosim node:20-alpine ca imagine de bază?
🔄 PARTEA 4: Cum Comunică Containerele
4.1 Rețeaua Docker
Cum comunică containerele între ele?
Ce este rețeaua Docker implicită?
De ce backend-ul poate accesa baza de date prin "db" și nu "localhost"?
Ce sunt hostname-urile în Docker?
4.2 Porturile și Maparea
Ce sunt porturile și cum funcționează?
De ce avem "1433:1433", "4000:4000", "8080:8080"?
Ce înseamnă "localhost:8080" din exterior vs interior?
Cum accesăm serviciile din afara containerelor?
🛢️ PARTEA 5: Baza de Date SQL Server
5.1 Containerul Bazei de Date
De ce folosim SQL Server într-un container?
Ce este "mcr.microsoft.com/mssql/server:2022-latest"?
Ce înseamnă "ACCEPT_EULA" și "SA_PASSWORD"?
Ce este "healthcheck" și de ce îl avem?
5.2 Schema Bazei de Date
Ce este schema.sql și cum se execută?
Ce tabele avem și cum se leagă între ele?
Ce sunt cheile primare și străine?
Cum am populat baza cu date inițiale?
🎭 PARTEA 6: Backend-ul (API Server)
6.1 Ce este Backend-ul?
Ce este o API și cum funcționează?
Ce înseamnă REST API și endpoint-uri?
Ce sunt metodele HTTP (GET, POST, PUT, DELETE)?
Ce este Express.js și de ce îl folosim?
6.2 Configurarea Backend-ului
Cum se instalează dependențele în container (npm install)?
Ce este JWT și cum funcționează autentificarea?
Ce este CORS și de ce e necesar?
Cum se conectează backend-ul la baza de date?
6.3 Environment Variables
Ce sunt variabilele de mediu și de ce le folosim?
Care sunt toate environment variables din backend?
Cum setăm JWT_SECRET și de ce e important?
De ce nu punem parolele direct în cod?
🖥️ PARTEA 7: Frontend-ul (Vue.js)
7.1 Ce este Frontend-ul?
Ce este Vue.js și de ce îl folosim?
Cum se construiește aplicația Vue (npm run build)?
Ce este "serve" și cum servește fișierele statice?
Ce sunt componentele Vue și cum funcționează?
7.2 Comunicarea cu Backend-ul
Ce este axios și cum face request-uri HTTP?
Cum configurăm URL-ul API-ului în frontend?
Ce este interceptorul axios pentru autentificare?
Cum gestionăm token-urile JWT în browser?
🔧 PARTEA 8: Procesul de Development
8.1 Construirea și Rularea
Cum pornim toate serviciile cu docker-compose up?
Ce se întâmplă când schimbăm codul?
Cum rebuild-uim containerele după schimbări?
Cum oprim și restart-ăm serviciile?
8.2 Debugging și Logs
Cum vedem log-urile containerelor?
Cum debug-uim probleme în containere?
Cum testăm API-ul independent de frontend?
Cum verificăm dacă serviciile comunică corect?
🚀 PARTEA 9: Workflow-ul Complet
9.1 De la Cod la Container
Care este ciclul complet: cod → build → container → rulare?
Cum se sincronizează schimbările cu volumes?
De ce uneori trebuie să rebuild-uim imaginile?
Care este diferența între development și production?
9.2 Dependințele dintre Servicii
De ce backend-ul depinde de baza de date?
De ce frontend-ul depinde de backend?
Ce este "depends_on" și "condition: service_healthy"?
În ce ordine pornesc serviciile?
🔍 PARTEA 10: Debugging și Problemele Întâlnite
10.1 Probleme Comune
De ce am avut 304 Not Modified și cache-ul browser-ului?
De ce JWT_SECRET lipsea și cum am rezolvat?
De ce URL-urile API erau inconsistente?
Cum am diagnosticat și reparat fiecare problemă?
10.2 Tools și Comenzi
Ce comenzi docker folosim frecvent?
Cum testăm API-ul cu curl?
Cum inspectăm containerele care rulează?
Cum accesăm shell-ul într-un container?
📊 PARTEA 11: Monitorizarea și Testarea
11.1 Health Checks
Ce sunt health check-urile și cum funcționează?
Cum verificăm dacă toate serviciile sunt ok?
Ce înseamnă statusurile: healthy, unhealthy, starting?
11.2 Testing API-ului
Cum testăm endpoint-urile unul câte unul?
Cum verificăm autentificarea și token-urile?
Cum testăm CORS și comunicarea cross-origin?
Cum validăm răspunsurile JSON?
🔒 PARTEA 12: Securitate și Configurare
12.1 Securitatea Containerelor
De ce nu punem parolele în Dockerfile?
Cum gestionăm secretele în Docker?
Ce este .dockerignore și de ce e important?
12.2 Configurarea Mediului
Cum diferă configurația pentru development vs production?
Ce ar trebui schimbat pentru a deploy-a în cloud?
Cum facem backup la baza de date în container?
🎯 Bonus: Întrebări Avansate pentru Viitor
Cum adăugăm un nou serviciu (ex: Redis cache)?
Cum facem load balancing cu multiple containere?
Cum implementăm CI/CD cu Docker?
Cum monitorizăm performance-ul containerelor?
Cum facem rolling updates fără downtime?
📝 Această listă acoperă tot ce trebuie să știi pentru a înțelege complet proiectul și partea de containere Docker. Fiecare întrebare te va ajuta să construiești o înțelegere solidă, pas cu pas!