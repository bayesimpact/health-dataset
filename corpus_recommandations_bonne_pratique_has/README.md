# Corpus HAS — Recommandations de bonne pratique

Ce fichier référence les documents sources du corpus, avec leurs liens de téléchargement officiels, plutôt que de committer les PDF binaires directement dans le repo.

## Contenu

325 documents "Recommandations de bonne pratique" publiés par la Haute Autorité de Santé (HAS), toutes disciplines confondues — voir [`liens_telechargement.txt`](./liens_telechargement.txt) pour la liste complète (titre, item HAS associé, nom de fichier et lien de téléchargement officiel pour chacun).

Généré à partir du manifeste de téléchargement local (`manifeste.csv`) constitué en scrapant [has-sante.fr](https://www.has-sante.fr).

## Utilisation prévue

Corpus source pour le pipeline d'extraction Q/A gradée (`bayesimpact/notebooks`, dossier `HAS/`, ex `evaluation_llm_has_sfar/`) — voir [`dataset_extraction_has_sfar.ipynb`](https://github.com/bayesimpact/notebooks) qui transforme un sous-ensemble de ces PDF en paires question/réponse gradées (grade GRADE/AVIS D'EXPERTS + argumentaire + polarité).

## Limites connues

- Le champ `year` n'existe pas dans cet export — pas de filtre d'ancienneté possible directement depuis ce fichier.
- Certains liens HAS (recommandations anciennes, ex. 2005) passent par une page intermédiaire plutôt qu'un lien PDF direct — signalé au cas par cas si besoin.
- Ce corpus recoupe partiellement le corpus consolidé SFAR documenté dans `bayesimpact/bayes-bench/docs/corpus-sfar.md` (voir `bayesimpact/internal-issues#70` pour la décision de migration en attente).
