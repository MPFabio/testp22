#Installer cli github :

#Pour Ubuntu-Debia
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
mkdir projetgit

#Se rendre dans le dossier crée
cd projetgit

#Créez son repo (mettre y pour le git clone pour l’importer)
gh repo create

#Se rendre dans le repo
cd test

#Modifiez le fichier README
echo ‘’blablabla’’ >> README.md

#Poussez les modification dans la Staging Area
git add README.md

#Poussez les modifications dans le Local Repo, l’option m permet d’ajouter un commentaire
git commit -m ‘’v.0.74’’

#Poussez les modifications dans le Remote Repo
git push https://github.com/MPFabio/test

#Créez un dossier pour le repo de son collègue
mkdir cedric

#Se rendre dans ce dossier
cd cedric

#Clonez le repo
git clone https://github.com/cedric69lt/repoindivcedric

#Se rendre dans le repo
cd repoindivcedric

#Mdifiez le fichier
echo ‘’blabla’’ > README.md

#Poussez les modification dans la Staging Area
git add README.md

# Poussez les modifications dans le Local Repo, l’option m permet d’ajouter un commentaire
git commit –m maj

#Poussez les modifications dans le Local Repo, l’option m permet d’ajouter un commentaire
git push https://github.com/cedric69lt/repoindivcedric
