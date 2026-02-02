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

## Préparation du VPS

Todo...

## Méthode de déploiement

Todo...
