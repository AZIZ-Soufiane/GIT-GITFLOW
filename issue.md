# Issue -> feature
gh issue view 321
git checkout -b feature/321-recherche-filtrage develop

# Dev avec petits commits
git commit -m "feat(search): ajouter filtres q/tag/sort (#321)"
git commit -m "test(http): couvrir /articles?tag= (#321)"

# Rester à jour
git pull --rebase origin develop
git push --force-with-lease

# Ouvrir PR
gh pr create --base develop --title "feat(search): filtres q/tag/sort (Closes #321)" --body-file PR.md

# Après review
gh pr merge --squash

# Nettoyage (si non auto)
git branch -d feature/321-recherche-filtrage
git push origin :feature/321-recherche-filtrage