# agendaJava
agenda en ligne de commande en Java

# Création de devoirs en ligne de commande

- envoi de notification android (package ntfy) et Windows (non determiné) quand la date approche
- enregistrement statique
- autocomplétion bash (plus tard)

## arguments de la commande:
- arg1: <create / modify / delete / verify>
- arg2: date
- arg3: matiere
- arg4: intitulé du devoirs
- arg5: [description]

[] = facultatif

## les classes requises
- Date(String): convertir et afficher les dates
    - int jour, int mois, int annee
    - toString(): renvoie une forme structurée de la date, si possible en affichant le jour de la semaine (package externe)

- Devoirs(Date, matiere, intitule, description): crée un devoirs et crée un identifiant unique (pour la modification ou la suppression)
    - Date date, String matiere, String intitule, String description, int identifiant
    - toString(): renvoie une forme structurée du devoirs

- Main(String[] args): programme principal qui gère les devoirs via les entrées de la ligne de commande. Vérifie si une échéance approche
    - verify(): Vérifie si une échéance arrive, envoie une notification si c'est le cas. (pourra être utilisé comme commande automatique)
    - create(String date, String matiere, String intitule, String description): crée un devoirs et l'enregistre en statique
    - modify(int identifiant, String date, String matiere, String intitule, String description): modifie un devoirs
    - delete(int identifiant): supprime un devoirs

### dépendances
- outil d'envoi de notification
- outil de convertion date -> jour de la semaine
- autocompletion bash
- outil gestion fichier (JSON / TXT)
