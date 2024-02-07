# NordVPN Bash Management Script

## Description
Ce script Bash permet de gérer facilement NordVPN sous Linux. 
Il offre des fonctionnalités telles que la connexion et la déconnexion à des serveurs spécifiques, 
la modification des paramètres du VPN, et la réinitialisation des paramètres DNS après la déconnexion.

Ce script a vu le jour suite aux problèmes de réinitialisation des paramètres DNS lors de la déconnexion de NordVPN sur un système Linux.
Lors d'une déconnexion manuelle, les paramètres DNS sont réinitialisés et le Kill Switch désactivé.
Lors d'une connexion manuelle, le Kill Switch est réactivé s'il ne l'est pas déjà.

## Fonctionnalités
- Connexion à NordVPN avec un choix de serveur spécifique ou aléatoire
- Déconnexion de NordVPN avec réinitialisation automatique des DNS
- Modification des paramètres NordVPN (protocole, technologie, etc.)
- Affichage de l'état actuel de la connexion VPN et des paramètres

## Prérequis
- NordVPN installé sur votre système Linux
- Certains droits sudo pour la réinitialisation des paramètres DNS (Utilisation de **truncate** et de **tee**)

## Utilisation
Pour une utilisation libre sans avoir à vous déplacer jusqu'au script, ajoutez le script à la variable d'environnement PATH.
De cette manière, il vous suffira de saisir **nvpn** suivi de l'option et des arguments peu importe votre localisation.

Voici les différentes options disponibles :
```bash
./nvpn --help        # Affiche l'aide
./nvpn --status      # Affiche l'état de la connexion VPN
./nvpn --enabled     # Active tous les paramètres passés en argument, séparés par un espace
./nvpn --disabled    # Désactive tous les paramètres passés en argument, séparés par un espace
./nvpn --technology  # Permet de modifier la technologie à utiliser 
./nvpn --protocol    # Permet de modifier le protocole à utiliser
./nvpn -s            # Affiches les paramètres courant et leur status
./nvpn -c            # Connecte à un serveur aléatoire
./nvpn -c FR         # Connecte au serveur VPN en France
./nvpn -d            # Déconnecte du VPN et réinitialise les DNS
```

## Configuration
J'ai pris la peine de réaliser ce script en intégrant un tableau associatif contenant les serveurs DNS les plus connus.
De cette manière, il est très simple d'en ajouter de nouveau et de modifier la sélection.

Si vous souhaitez désactiver la réinitialisation des paramètres DNS, 
il vous suffit de mettre la variable **DNS_SELECTED** en commentaire, 
mais de ce fait ce script ne vous sera plus réellement utile.

## Licence
Ce script est entièrement gratuit, du simple partage entre passionnés, si vous en avez l'utilité, alors servez-vous.
