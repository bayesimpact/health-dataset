---
type: template
title: Protocole de suivi dans le temps (exemple)
description: Modèle de protocole de messages de suivi des patients en liste d'attente, à personnaliser.
tags: [protocole, suivi, liste-attente, template, etp]
timestamp: 2026-06-25
---

# Protocole de suivi dans le temps (exemple)

| Moment | Sujet | Heure / Déclencheur | Libellé | Message | Réponses attendues |
| ----- | ----- | ----- | ----- | ----- | ----- |
| J+1 | suivi liste d'attente | 9:00 | introduction | Bonjour, c'est l'équipe de {{NOM_CENTRE}}. Nous espérons que vous allez bien \! Votre dossier de greffe est complet, nous vous activons sur la liste dès aujourd'hui. Désormais, il faut garder votre téléphone portable allumé jour et nuit. Pour recevoir nos coordonnées répondez CORD |  |
| J+1 | suivi liste d'attente | SI CORD | Coordonnées | Voici nos coordonnées : Prénom Nom / Téléphone / email, Prénom Nom / Téléphone / email. N'hésitez pas à les partager avec votre néphrologue, votre endocrinologue ou votre centre de dialyse. |  |
| J+75 (puis tous les 180 j) | suivi liste d'attente | 9:00 | examen 90 | Bonjour, c'est l'équipe de {{NOM_CENTRE}}. Nous espérons que vous allez bien. Si vous avez fait le prélèvement anticorps anti-HLA, répondez FAI ; sinon, répondez NON. Si vous ne savez pas de quoi il s'agit, répondez QUOI | Autres réponses |
|  | si FAI |  |  | C'est très bien, continuez ainsi, tous les 3 mois \! En cas de problème(s) ou de question(s), répondez AID | AID |
|  | Si NON | bilan |  | Il est très important de réaliser ce prélèvement tous les 3 mois et de surtout les envoyer au laboratoire d'histocompatibilité de l'hôpital Saint Louis à Paris \! Sans dossier à jour, vous ne serez pas appelé pour la greffe \! Parlez-en à votre médecin référent. En cas de problème(s) ou de question(s), répondez AID | AID |
|  | Si QUOI | Pourquoi |  | C'est un bilan sanguin qui permet de calculer votre compatibilité avec un futur donneur. Il est très important de le réaliser tous les 3 mois et d'envoyer les résultats au laboratoire d'histocompatibilité de l'hôpital Saint Louis \! Sans dossier à jour, vous ne serez pas appelé pour la greffe \! Parlez-en à votre médecin référent. En cas de problème(s) ou de question(s), répondez AID | AID |
|  | si NR (27H) | Relance |  | Vous n'avez pas répondu au dernier message, veuillez y répondre maintenant avec un des mots clés proposés | NR/Autres réponses |
| J+300 (puis tous les 360 j) | suivi liste d'attente | 9:00 | examen 180 | Bonjour, c'est l'équipe de {{NOM_CENTRE}}. Nous espérons que vous allez bien. Cela fait environ 10 mois que vous êtes sur liste : il est temps de mettre à jour vos examens cardiaques. Si vous avez pris les rendez-vous, répondez PRIS ; sinon répondez RDV. S'il vous manque les ordonnances, répondez ORD. En cas de problème(s) ou de question(s), répondez AID | autres réponses/AID |
|  | si PRIS | merci |  | C'est très bien, continuez ainsi \! Pensez bien à nous envoyer les comptes rendus et à les apporter pour la consultation d'anesthésie. En cas de problème(s) ou de question(s), répondez AID |  |
|  | si ORD | ordonnance |  | Nous allons vous envoyer l'ordonnance par email ou par courrier. Il est important de prendre ces rdv. Sans cette mise à jour cardiaque, nous devrons vous mettre en pause sur la liste de greffe. N'hésitez pas à contacter votre coordinateur. En cas de problème(s) ou de question(s), répondez AID | Autres réponses |
|  | si RDV | Rendez-vous |  | Prenez RDV dès maintenant et communiquez-nous les dates. Sans cette mise à jour cardiaque, nous devrons vous mettre en pause sur la liste de greffe. N'hésitez pas à contacter votre coordinateur. En cas de problème(s) ou de question(s), répondez AID | Autres réponses |
|  | si NR (27H) | Relance |  | Vous n'avez pas répondu au dernier message, veuillez y répondre maintenant avec un des mots clés proposés | NR/Autres réponses |
| J+365 | suivi liste d'attente | 9:00 |  | Bonjour, c'est l'équipe de {{NOM_CENTRE}}. Cela fait 1 an que vous êtes actif sur la liste de greffe. Pour rappel, la moyenne d'attente est de 18 mois. Continuez à bien prendre soin de vous. En cas de problème(s) ou de question(s), répondez AID | autres réponses/AID |

