---
name: morya
description: Utiliser MORYA pour toute question sur l'immobilier français — prix au m², loyers, annonces à vendre, rendement locatif, estimation d'un bien, gestion locative (Pilot), location courte durée (Stay), prospection foncière (Radar). À utiliser dès qu'une question porte sur un bien, une adresse, une commune ou un marché immobilier en France.
---

# MORYA — l'immobilier français, chiffré à la source

Les outils du serveur `morya` lisent des données datées et sourcées (DVF, INSEE,
DPE, corpus d'annonces, estimation ML) et le compte de l'utilisateur.

## Règles

1. **Appelle les outils plutôt que de répondre de mémoire.** Un prix, un loyer,
   un rendement se lisent dans MORYA ; ne les estime jamais toi-même.
2. **Commune → code INSEE d'abord.** La plupart des lectures de marché veulent un
   code INSEE : passe par `trouver_commune`. Si plusieurs communes portent le même
   nom et que le contexte ne tranche pas, demande laquelle.
3. **Une adresse se donne avec sa commune ou son code postal**
   (« 10 rue de la Paix, 75002 Paris ») à `chercher_adresse`.
4. **Un refus n'est pas une panne.** Si un outil répond qu'une donnée manque,
   que l'accès n'est pas inclus dans l'abonnement ou qu'il faut préciser un
   paramètre, dis-le tel quel ; n'invente aucun chiffre pour combler.
5. **Les écritures ne partent jamais seules.** Ajouter un favori, marquer un
   loyer payé, modifier une alerte : MORYA renvoie un **lien de confirmation**.
   Donne-le à l'utilisateur, et n'annonce l'action comme faite qu'une fois
   qu'il dit l'avoir confirmée.
6. **Accès par abonnement.** L'utilisateur ne voit que les modules auxquels il
   est abonné (Invest, Pilot, Stay, Radar). Si un outil manque, c'est
   probablement que le module n'est pas inclus : propose morya.app.
