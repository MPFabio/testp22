#Installez cli github :

#Pour Ubuntu-Debian

type -p curl >/dev/null || (sudo apt update && sudo apt install curl -y)
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
&& sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y

#Pour Windows

winget install --id GitHub.cli 

#Authentifiez vous avec votre compte github

gh auth login

#Créez un dossier pour votre repo

mkdir nom_dossier

#Se rendre dans le dossier crée

cd nom_dossier

#Créez son repo (mettre y pour le git clone pour l’importer)

gh repo create

#Se rendre dans le repo

cd nom_repo

#Modifiez le fichier README

echo "blablabla" >> README.md

#Poussez les modification dans la Staging Area

git add README.md

#Poussez les modifications dans le Local Repo, l’option m permet d’ajouter un commentaire

git commit -m "votre_commentaire"

#Poussez les modifications dans le Remote Repo

git push lien_repo_github

#Créez un dossier pour le repo de son collègue

mkdir nom_dossier

#Se rendre dans ce dossier

cd nom_dossier

#Clonez le repo

git clone lien_repo_github

#Se rendre dans le repo

cd nom_repo

#Mdifiez le fichier

echo "blabla" > README.md

#Poussez les modification dans la Staging Area

git add README.md

#Poussez les modifications dans le Local Repo, l’option m permet d’ajouter un commentaire

git commit –m "votre_commentaire"

#Poussez les modifications dans le Local Repo, l’option m permet d’ajouter un commentaire

git push lien_repo_github
