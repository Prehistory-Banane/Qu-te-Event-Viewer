# Quête Les-logs

## 1. Installer un serveur web (Apache ou Nginx), ici Nginx sur une machine virtuelle Linux
### Pour revoir comment installer nginx, aller sur l'adresse suivante :
https://www.it-connect.fr/debian-comment-installer-nginx-en-tant-que-serveur-web/


Vérifier que le serveur Nginx est installé :  
![1](https://github.com/user-attachments/assets/2e84fcb2-f89c-4204-8c88-078a3546193d)


Le retour de la commande indique que le serveur est installé. :white_check_mark:  

---
## 2. Configurer le logging pour enregistrer les accès et les erreurs  

Par défaut, le fichier de configuration de Nginx se trouve dans ``/etc/nginx/nginx.conf``.  
Il faut ensuite s'assurer que ces 2 lignes sont décommentées, elles enregistrent les erreurs d'Apache pour la première et les requêtes pour la deuxième :  
``error_log /var/log/nginx/error.log``  
``access_log /var/log/nginx/access.log``  

Dans le cas où elles sont commentées, il faut décommenter et relancer le service (pour rappel ``systemctl restart nginx``). :white_check_mark:  

---
## 3. Généner du trafic sur le serveur web (utilise des outils comme curl ou un navigateur)  

Pour générer des logs, il faut lancer des requêtes.  
J'ai installé l'outil **"Curl"**, (``apt install curl``) qui permet de faire des requêtes HTTP en lignes de commandes.  
J'ai ensuite lancé plusieurs requêtes :  
``curl http://localhost`` # Cette requête va réussir. Elle sert à vérifier que mon serveur web fonctionne bien.  
``curl http://127.0.0.1`` # Cette requête va réussir. Elle sert à vérifier que mon serveur web fonctionne bien.  
``curl http://localhost/echec`` # Cette requête va échouer, car la page est inextistante.   
:white_check_mark:  

---
## 4. Analyser les logs générés et identifie :  
pour afficher les accès au serveur Apache.  
``cat /var/log/nginx/access.log``  

* ### Une requête réussie (code 200)
![2](https://github.com/user-attachments/assets/46413349-5d85-49b2-a3f4-937fbc9e45f2)
La machine locale (`127.0.0.1`) a effectué une requête qui a abouti (code 200). :white_check_mark:   

* ### Une erreur 404 (page non trouvée)  
![3](https://github.com/user-attachments/assets/02690527-e193-4532-807b-2a943dfb0e6f)
La machine locale (`127.0.0.1`) a effectué une requête qui n'a pas abouti (code 404), car la page "blabla" n'existe pas. :white_check_mark:  

* ### Les IP les plus fréquentes  
Dans mon cas il n'y a quasiment pas de traffic.  
![4](https://github.com/user-attachments/assets/f0fb44ff-0e90-4fd0-b21a-61d119ca1cc3)
l'unique adresse est l'adresse locale. :white_check_mark:  
