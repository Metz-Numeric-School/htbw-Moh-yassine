# Procédure de Déploiement

# PROCÉDURE A SUIVRE : 

Etape 1 : Connexion en SSH a Debian pour tester la connexion  -> ssh root@192.168.23.137 

Etape 2 : git clone (https://github.com/Metz-Numeric-School/htbw-Moh-yassine.git)  
  
Etape 3 : Installer les dépendances composer install --optimize-autoloader   
  
Etape 4 : Vérifier que le fichier fonctionne sur notre PC 

Etape 5 : Lancer le projet en passant par la commande : `php bin/serve`
  
Etape 6 : Installer GitCliff  
Terminal : brew install git-cliff 
  
Terminal : git-cliff --init  
  
Terminal : git add .  
  
Terminal : git commit -m "doc:First commit"  
  
Terminal : git-cliff --bump -o ./CHANGELOG.md  
  
Voir la version générée dans CHANGELOG.mg  
  
Terminal : git add .  
  
Terminal : git commit -m "version [tag]"  
  
Terminal : git tag [tag]  
  
Terminal : git push origin main  

# Site web de aaPanel: 
  
Etape 7 : Installer aaPanel  
Sur le serveur Debian (via SSH) : URL=https://www.aapanel.com/script/install_7.0_en.sh && if [ -f /usr/bin/curl ];then curl -ksSO "$URL" ;else wget --no-check-certificate -O install_7.0_en.sh "$URL";fi;bash install_7.0_en.sh aapanel

Site web de aaPanel avec le lien  
  
Noter : Identifiant, mot de passe donné, 2ème adresse IP  
  
Navigateur : Ouvrir la 2ème adresse IP  
  
Navigateur : Forcer l’ouverture de la page non sécurisée  
  
Navigateur : Se connecter avec les identifiants donnés  
  
Navigateur : Sélectionner LNMP (One-click)  
  
Laisser l’installation se faire (profiter pour faire la doc)  

Navigateur : Se rendre dans l’onglet "Website" à gauche  
  
Navigateur : Cliquer sur le bouton "Add site"  
  
Navigateur : Noter le nom de domaine fournis par MNS dans "Domaine name"  
  
Navigateur : Sélectionner "Create" sur le champ "FTP"  
  
Noter : FTP settings, Password  
  
Navigateur : Sélectionner "MySQL" sur le champ "Database"  
  
Noter : Database settings, Password  
  
"Database settings" sera le nom et l’identifiant de la BDD  
  
"Password" sera le mot de passe de la BDD  
  
Navigateur : Cliquer sur le bouton "Confirm"  
  
Navigateur : Fermer la modale avec les identifiants  
  
Etape 7 : Déployer  
Terminal :  cd /  
  
Terminal :  ls /www/wwwroot  
  
Sur le serveur (via SSH) : cd /  
  
Sur le serveur (via SSH) : ls /www/wwwroot  
  
Vérifier qu’il y a bien un fichier avec l’IP fournis par MNS  
  
Sur le serveur (via SSH) : mkdir -p /var/depot_git  
  
Sur le serveur (via SSH) : cd /var/depot_git  
  
Sur le serveur (via SSH) : git init --bare  
  
Terminal (macOS) : git remote add vps root@[adresse_ip]:/var/depot_git  
  
Terminal (macOS) : git push -u vps [tag]  
  
Sur le serveur (via SSH) : cd /  
  
Sur le serveur (via SSH) : sudo touch /deploy.sh  
  
Sur le serveur (via SSH) : sudo nano /deploy.sh  
  
Sur le serveur (via SSH) (dans /deploy.sh) git --work-tree=/www/wwwroot/[adresse_ip] --git-dir=/var/depot_git checkout -f $1  
  
Sur le serveur (via SSH) : Quitter le fichier (ctrl+X, O, Entrer)  
  
Sur le serveur (via SSH) : sudo chmod +x /deploy.sh  
  
Sur le serveur (via SSH) :
Navigateur : Se rendre dans l’onglet "Site directory"  
  
Navigateur : Noter "/public" sur le champ "Running directory"  
  
Navigateur : Désactiver le "XSS attack"  
  
Navigateur : Se rendre dans l’onglet "SSL"  
  
Navigateur : Sélectionner "Let’s Encrypt"  
  
Navigateur : Cocher le nom de domaine  
  
Navigateur : Cliquer sur le bouton "Apply"  
  
Navigateur : Se rendre dans l’onglet "Composer"  
  
Navigateur : Fermer la modale  
  
Etape 9 : Variables d'environements  
VSCode : Modifier les variables d'environements  
  
Navigateur : Dérouler "New" et selectionner "New blank file" et le nomer ".env"  
  
Navigateur : Modifier les variables d'environements  
  
Navigateur : Fermer et enregistrer le fichier  
  
Etape 10 : Chaque commit (après chaque résolution de bug)  
Terminal : VSCode git add .  
  
Liste des mots clés dans cliff.toml  
  
Terminal (macOS) : git add .  
  
Liste des mots clés dans cliff.toml  
  
Terminal (macOS) : git commit -m "[mot_clé]:[commentaire]"  
  
Terminal (macOS) :
Liste des mots clés dans cliff.toml  
  
Terminal (macOS) : git add .  
  
Liste des mots clés dans cliff.toml  
  
Terminal (macOS) : git commit -m "[mot_clé]:[commentaire]"  
  
Terminal (macOS) : git add .  
  
Terminal : VSCode git commit -m "version [tag]"  
  
Terminal : VSCode git tag [tag]  
  
Terminal : VSCode git push origin main  
  
Terminal : VSCode git push vps [tag]  
  
Terminal :  bash /deploy.sh [tag]  

