

Aduce **noutățile** de pe remote **fără** să le combine în branchul tău.**actualizează pointerele locale** de tip _remote-tracking_ (ex. `origin/main`

git fetch origin
sau doar o ramură:
git fetch origin main


git log --oneline --graph HEAD..origin/main
git diff --stat HEAD..origin/main
