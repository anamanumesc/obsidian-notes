
- **PR** (GitHub) = **MR** (GitLab / Azure DevOps)
- Ambele sunt cereri de integrare a codului într-un branch principal



- Creezi un branch (ex: `feature/add-login`).
- Faci commit-uri → `push`.
- Creezi un **PR/MR** spre `develop` sau `main`.
- Pipeline-ul CI/CD rulează automat (teste, build, linting etc.).
- Echipa de **reviewers** (alți developeri sau DevOps) verifică codul.
- După aprobare → se face **merge** automat sau manual.