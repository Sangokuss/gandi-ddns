Gandi-ddns est un script Python pour faciliter la mise à jour des enregistrement DNS avec l'application gandi.net LiveDNS.

Cet outil est particulièrement utile pour les utilisateur auto-hébergeant leurs serveurs à la maison et ne disposant pas d'une adresse IP fixe, mais possédant un nom de domaine chez Gandi.net.

Pour information, vous trouverez diverses informations complémentaires sur LiveDNS ici : http://doc.livedns.gandi.net/

Enfin, notez que ce script est un fork de l'excellent travail suivant : https://github.com/rmarchant/gandi-ddns

Installation sur Debian 10.7.1 (testé et validé dans un container non privilégié Proxmox) :
- après installation d'une Debian 10, veuillez réaliser les mises à jour si cela s'avère nécessaire :
```
~# apt update
~# apt upgrade
```
- l'utilisation de Python3.7 est recommandée, il faut donc l'installer
```
~# apt install python3.7
```
- télécharger ensuite le zip (master.zip) dans /home/"user"
```
~# wget <url du master.zip de ce dépôt>
```
/!\ Il vous faudra ensuite récupérer votre API key sur le site gandi.net (dans l'ongle "sécurité" de votre interface d'administration ;-) )

- la clé devra ensuite être renseigner dans les fichiers *.txt (tout comme les types/noms des enregistraments au sein de ces mêmes fichiers).
- Indispensable : pensez à vérifier que tout est bien installé (dans mon cas, je n'avais rien eu à faire, mais un contrôle des dépendances est conseillé via la commande suivante : 
```
~# pip3 install -r requirements.txt
```
/!\ si la commande "pip3" ne fonctionne pas, c'est qu'il faut tout simplement installer python-pip3 ;-)

- Enfin il ne reste plus qu'à rédiger les tâches cron nécessaire pour l'actualisation. Tout comme l'auteur initial du script d'origine, je vous recommande d'utiliser la récurrence suivante :

```
2-59/15 * * * * python /home/user/gandi-ddns.py
```
Et voilà, un reboot (au cas où) et tout devrait fonctionner sans souci !
Sangokuss.
