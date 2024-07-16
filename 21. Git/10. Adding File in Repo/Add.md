Same process of Local git just we have to follow the step given by the repo.

For Refarance->

echo "# REPO_NAME" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/USERNAME/REPO_NAME.git
git push -u origin main

For Existing Repo

git remote add origin https://github.com/USERNAME/REPO_NAME.git
git branch -M main
git push -u origin main
