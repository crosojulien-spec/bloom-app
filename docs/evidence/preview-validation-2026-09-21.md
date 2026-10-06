# Validation BlooM en prévisualisation — 21 septembre 2026

## Verdict

**SHIP pour la prévisualisation de développement.**

- Aucune publication effectuée.
- Aucun paiement appelé.
- Aucune synchronisation Airtable ni aucun e-mail exécuté pendant les parcours QA.
- La base et l'IA de développement ont été utilisées comme prévu.

## Changements validés

- Invitations QA locales, réservées au développement, avec création, lecture publique, liste admin sans jeton, et transitions `PENDING`, `USED`, `EXPIRED`.
- Refus des invitations QA en production : création, liste, changement de statut et lecture d'un jeton QA retournent `404`.
- Reprise navigateur du parcours complet grâce à la persistance de session du dossier, des menus générés, des sélections client, des propositions chef et du statut.
- Confirmation finale atomique et idempotente : `finalMenu` et `SENT_TO_CLIENT` sont écrits ensemble ; un double appel concurrent et une reprise séquentielle retournent une seule confirmation normale puis `deduplicated: true`.
- Les corrections manuelles de packs professionnels ne peuvent pas être écrasées par une génération IA tardive.

## Parcours Le Tôt ou Tard

- Conversation Benkei, corrections de date et de goûts, génération réelle et menu `5/5/5`.
- Double clic de génération : un seul appel réseau.
- Une sélection par service, note client, adaptation chef et une proposition finale.
- Bougie discrète conservée comme demande **« à confirmer avec le restaurant »**, sans promesse.
- Confirmation simulée terminée sans route de paiement.
- Packs Chef et Salle corrigés, rechargés et approuvés.
- Pack Salle : réserve « à confirmer » conservée.
- Statuts e-mail des deux packs : `NOT_SENT`.

## Parcours Lá Bù Lá

- Conversation Benkei complète en français : 3 personnes, horaire, piment moyen, absence d'allergie/régime, souvenir de bouillon partagé.
- Correction persistante après rechargement : date `2026-10-19` et goûts `bouillon chaud, aubergine`.
- Petit mot manuscrit affiché et stocké comme **« à confirmer avec le restaurant »** et **non garanti**.
- Un seul appel de génération, avec exactement 5 entrées, 5 plats et 5 desserts.
- Une sélection par service, note client et adaptation chef « QA Lá Bù Lá adaptation ».
- Rechargement de la page finale : proposition, plats, contexte et adaptation restaurés.
- Confirmation simulée : un seul appel réseau dans le parcours navigateur, réponse `200`.
- Réouverture de l'invitation : état terminal `USED`.
- Packs Chef et Salle corrigés, rechargés et approuvés ; statuts e-mail `NOT_SENT`.

## Résilience et isolation

- Deux confirmations concurrentes sur le correctif final :
  - une réponse normale `200` ;
  - une réponse `200` avec `deduplicated: true`.
- Nouvelle confirmation séquentielle : `200`, `deduplicated: true`.
- Un seul traitement asynchrone observé dans les logs.
- Deux packs uniques, tous deux `APPROVED`.
- Une invitation d'un autre restaurant ne peut pas confirmer le dossier : `403`.
- Cycle d'invitation QA vérifié jusqu'à `EXPIRED`, puis lecture publique `410`.
- Jetons absents de la liste admin.
- Un ancien dossier distinct reste consultable après les deux nouveaux parcours.
- Une réponse IA tardive a été refusée après une correction manuelle ; le contenu corrigé est resté intact.

## Décompte des routes

Le nombre `30/29` venait de deux périmètres différents :

- **Avant** la nouvelle route de statut QA : **30 routes Express au total**, dont **29 routes `/api/*`**, plus `GET /status`.
- **Après** l'ajout de `PATCH /api/invitations/:token/status` : **31 routes Express au total**, dont **30 routes `/api/*`**, plus `GET /status`.

Il n'y a pas de doublon de méthode et chemin.

## Contrôles finaux

- Tests qualité : **29/29 réussis**.
- TypeScript application : réussi.
- TypeScript qualité : réussi.
- Build Vite + serveur : réussi.
- `git diff --check` : réussi.
- Revue architecturale finale : **SHIP**, aucun problème bloquant ou élevé.

## Observations non bloquantes

- Le premier chargement après redémarrage peut afficher brièvement l'écran de préparation de la prévisualisation.
- Après correction manuelle de la date, le récapitulatif peut signaler la contradiction avec la date formulée dans la conversation initiale. La correction manuelle reste prioritaire, persistante et validable.
- Le choix radio du menu final n'est pas conservé après rechargement : la proposition et tout son contexte sont restaurés, mais le client doit sélectionner de nouveau le menu avant la confirmation simulée. Cela évite une confirmation involontaire après reprise.