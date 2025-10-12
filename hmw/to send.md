CERINTA: Deploiați și rulați local o aplicație existentă de tip 3-tier (front-end, back-end, bază de date), de preferat preluată dintr-un repository GitHub. Front-end-ul trebuie să trimită cereri către back-end, iar back-end-ul să proceseze datele și să le persiste în baza de date. Fiecare componentă rulează în container separat. Utilizarea Django și WordPress nu este permisă.


nu vr sa o fac pe auzre nepaarat vr sa o fac pe altceva acuma. vreau codul asta sa l fac pe altceva. vr 1. sa respecte cerinta temei. 2. sa fie public website ul (sa fie cu domain) 3. sa fie cat mai simplu. 4. sa folosecs codul meu de pe github. 5. eu vreau doar sa pastrez functionalitatea de front si de back gen, nu vreau sa mai rescriu logica de backend si frontend. dar pot sa schimb serviciile gen nu ma deranjeaza daca schimb total serviciile sau ce baza de date folosesc. doar de codul de backend so frontend imi pasa ATAT. ok? deci te rog keep it as simple as possible

**

CODUL MEU DE PE GITHUB:

- Book Exchange Platform (Azure, Node.js, Vue.js, SQL Database)

- Collaborated in a team of 4 to design and deploy a multi-tier web application on Microsoft Azure, helping users find books available for exchange in their city and propose a trade
    
- Integrated an email service API to enable communication between users    

Used and orchestrated multiple Azure services (App Service, SQL Database, Blob Storage, Azure Functions) to build a scalable and persistent application**

r>[66f9d56](https://github.com/anamanumesc/SchimbDeCartiRomania/commit/66f9d56d3ba7fd858a3f8b6f5f507668ff979bf3) · 5 months ago|   |   |
|[backend](https://github.com/anamanumesc/SchimbDeCartiRomania/tree/main/backend "backend")|[i debugged the requests functionality](https://github.com/anamanumesc/SchimbDeCartiRomania/commit/20f8a711f2c9d9fe6a5bbc75ac8771252f8b2b77 "i debugged the requests functionality")|5 months ago|
|[frontend](https://github.com/anamanumesc/SchimbDeCartiRomania/tree/main/frontend "frontend")|[updated city list](https://github.com/anamanumesc/SchimbDeCartiRomania/commit/66f9d56d3ba7fd858a3f8b6f5f507668ff979bf3 "updated city list")|5 months ago|
|[.DS_Store](https://github.com/anamanumesc/SchimbDeCartiRomania/blob/main/.DS_Store ".DS_Store")|[Initial commit: SchimbDeCartiRomania application](https://github.com/anamanumesc/SchimbDeCartiRomania/commit/3c4ff8df062c423eecc1875b869fa759bd9ad72a "Initial commit: SchimbDeCartiRomania application")|5 months ago|
|[.gitignore](https://github.com/anamanumesc/SchimbDeCartiRomania/blob/main/.gitignore ".gitignore")|[map for book city location](https://github.com/anamanumesc/SchimbDeCartiRomania/commit/63ec7501d33de26bbff6549acdac5716ed3457f5 "map for book city location")|5 months ago|
|[README.md](https://github.com/anamanumesc/SchimbDeCartiRomania/blob/main/README.md "README.md")|[i debugged the requests functionality](https://github.com/anamanumesc/SchimbDeCartiRomania/commit/20f8a711f2c9d9fe6a5bbc75ac8771252f8b2b77 "i debugged the requests functionality")|5 months ago|
|[package-lock.json](https://github.com/anamanumesc/SchimbDeCartiRomania/blob/main/package-lock.json "package-lock.json")|[map for book city location](https://github.com/anamanumesc/SchimbDeCartiRomania/commit/63ec7501d33de26bbff6549acdac5716ed3457f5 "map for book city location")|5 months ago|
|[package.json](https://github.com/anamanumesc/SchimbDeCartiRomania/blob/main/package.json "package.json")|[map for book city location](https://github.com/anamanumesc/SchimbDeCartiRomania/commit/63ec7501d33de26bbff6549acdac5716ed3457f5 "map for book city location")|5 months ago|
|[technical_report-cloud.docx](https://github.com/anamanumesc/SchimbDeCartiRomania/blob/main/technical_report-cloud.docx "technical_report-cloud.docx")|[Add files via upload](https://github.com/anamanumesc/SchimbDeCartiRomania/commit/bec1f918e45a9ce2aafa2480139593f5b0234b27 "Add files via upload")|5 months ago|

## Repository files


navigation

- [README](https://github.com/anamanumesc/SchimbDeCartiRomania?tab=readme-ov-file#)

# schimb-de-carti-romania

[](https://github.com/anamanumesc/SchimbDeCartiRomania?tab=readme-ov-file#schimb-de-carti-romania)

## frontend setup

[](https://github.com/anamanumesc/SchimbDeCartiRomania?tab=readme-ov-file#frontend-setup)

```
1. cd frontend
2. cd schimb-de-carti-romania
3. node -v
4. npm -v
5. npm install -g @vue/cli
6. npm install
7. npm install axios
8. chmod +x node_modules/.bin/vue-cli-service
9. npm run serve



## backend setup 
1. cd backend (in alt terminal)
2. npm install express cors mssql dotenv
3. trebuie sa adaugi in baza de date adresa ta IP 
4. node server.js




5. go to http://localhost:8080/ 



                                      ┌───────────────┐
                                      │   /login      │ ←─ Autentificare utilizator
                                      └──────┬────────┘
                                             │
                                      ┌──────▼────────┐
                                      │   /signup     │ ←─ Creare cont nou
                                      └──────┬────────┘
                                             │
                                      ┌──────▼────────┐
                                      │ /forgot-password │ ←─ Resetare parolă
                                             │
                                             ▼
    ┌────────────────────────────────────────────────────────────────────────┐
    │                                / (HomePage)                            │
    │ - Listă de cărți disponibile pentru schimb                            │
    │ - Posibil filtrare după oraș/categorie                               │
    └──────┬────────────────────────────────────────────────────────────────┘
           │
           │
    ┌──────▼───────────────────────────────────────────────────────────────┐
    │ /book/:id (BookPage)                                                 │
    │ - Pagina detaliată a unei cărți                                      │
    │ - Buton de propunere schimb                                          │
    └──────┬───────────────────────────────────────────────────────────────┘
           │
           ▼
    ┌──────────────────────────────────────────────────────────────────────┐
    │ /book/:id/propose (ProposeExchangePage)                              │
    │ - Form pentru a propune un schimb cu cartea respectivă              │
    └──────────────────────────────────────────────────────────────────────┘

    ┌──────────────────────────────────────────────────────────────────────┐
    │ /add (AddBookPage)                                                   │
    │ - Form pentru a adăuga o carte în platformă                         │
    └──────────────────────────────────────────────────────────────────────┘

    ┌──────────────────────────────────────────────────────────────────────┐
    │ /account (AccountPage)                                               │
    │ - Profilul propriu: informații personale, cărțile mele etc.         │
    └──────────────────────────────────────────────────────────────────────┘

    ┌──────────────────────────────────────────────────────────────────────┐
    │ /requests (MyRequestsPage)                                           │
    │ - Listă de cereri de schimb trimise și primite                      │
    └──────────────────────────────────────────────────────────────────────┘

    ┌──────────────────────────────────────────────────────────────────────┐
    │ /profile/:id (PublicProfilePage)                                     │
    │ - Profil public al altui utilizator                                 │
    │ - Afișează cărțile acestuia și info publice                          │
    └──────────────────────────────────────────────────────────────────────┘
```


## My recommendation for you

- **Do the homework with SchimbDeCartiRomania** (Option A). Keep the assignment scope tiny: just front/back/DB in 3 containers.
    
- When the homework is done, you already have the artifacts you need to d your personal project:
    
    1. push images to **ECR**,
        
    2. run backend on **Lightsail/ECS**,
        
    3. publish frontend to **S3 + CloudFront**,
        
    4. switch DB to **Postgres** (cheap),
        
    5. add **GitHub Actions** CI/CD.