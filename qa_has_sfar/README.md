# Jeux de questions/réponses — recommandations HAS/SFAR

Deux jeux de questions/réponses cliniques construits à partir de recommandations officielles françaises (HAS, SFAR), pour évaluer des LLM et des agents RAG sur leur fidélité aux recommandations.

| Fichier | Contenu | Méthode | Statut |
|---|---|---|---|
| `qa_rfe_sfar.json` | 174 questions, 700 recommandations gradées, 27 documents (RFE/RPP SFAR, RBP résection hépatique) | Extraction par règles (regex), sans appel à un LLM | Sous-ensemble du jeu évalué le 04/09/2026 (180 questions), voir « Limites connues » |
| `qa_rbp_has_pilote.jsonl` | 28 questions, 14 documents, issues des 325 Recommandations de bonne pratique HAS | Extraction assistée par LLM, citations vérifiées automatiquement | Pilote, grilles non relues par un clinicien |

Les PDF sources ne sont pas redistribués ici. Les liens officiels des 325 RBP sont dans [`corpus_recommandations_bonne_pratique_has/`](../corpus_recommandations_bonne_pratique_has/).

## `qa_rfe_sfar.json`

Une entrée par question clinique posée dans le document source. Une question n'est gardée que si au moins une de ses recommandations porte un grade explicite : on préfère exclure une question que la garder avec une référence non fiable.

```json
{
  "document": "rac orthepedie lourde",
  "champ_id": "4",
  "champ_title": "",
  "question_id": "4",
  "question_text": "Question 4 : Une prémédication avec de la gabapentine en périopératoire d’arthroplastie du…",
  "question_page": 16,
  "origin": "extracted_gradepm",
  "language": "fr",
  "country": "France",
  "authority": "HAS / SFAR",
  "answers": [
    {
      "rec_id": "R2",
      "grade": "GRADE 2- (accord FAIBLE)",
      "grade_confidence": "explicite",
      "text": "Il n’est probablement pas recommandé d’utiliser systématiquement les gabapentinoïdes en pé…",
      "rationale": "Cette question a fait l’objet d’une analyse récente par la SFAR dans le cadre des RFE sur …",
      "polarity": "négative",
      "polarity_confidence": "déduit du grade (signe GRADE, fiable)",
      "page": 16
    }
  ]
}
```

- **`origin`** : le parseur utilisé selon la structure du document. `extracted_gradepm` (format `Question N` / `GRADE 1±/2±`, 140 questions), `extracted_pico` (format `Question X.Y` / `R X.Y.Z`, 24), `extracted_champ_unnumbered` (format `CHAMP N` avec questions non numérotées, 10, récupération partielle).
- **`grade_confidence`** : `explicite` (593 recommandations) ou déduit d'un mot-clé comme « suggèrent » (107).
- **`polarity`** : sens de la recommandation (`positive` 259, `négative` 99, absente 342). **Seule la polarité déduite du signe du grade est fiable** ; celle déduite par regex sur le texte n'a pas été validée par un clinicien.
- **`rationale`** : l'argumentaire, utile comme contexte pour une condition « recommandation fournie ». Il contient souvent la conclusion en toutes lettres.

## `qa_rbp_has_pilote.jsonl`

Une ligne par question, au format du harnais de notation pondérée inspiré de HealthBench : `prompt` (la question, en registre professionnel), `context`, `brevity_priority` et `rubric` (critères avec points, tags, `recommendation_grade` et `source`). Le grade n'est renseigné que s'il figure dans le texte source (absent pour 11 questions).

## Limites connues

- 27 documents exploités sur 50 dans le corpus de travail SFAR ; 2 documents à structure non standard ne produisent aucune question.
- 2 documents du jeu évalué le 04/09 (RFE « Anesthésie du sujet âgé » et « Anesthésie loco-régionale périnerveuse », 6 questions) ont été retirés : les PDF utilisés étaient des versions éditeur sous droits, non redistribuables.
- La neutralité de la formulation des questions n'a pas été revue.
- Le jeu RBP est un pilote : les critères et leurs points doivent être relus par un clinicien avant un usage officiel.
- Les adresses email présentes dans les argumentaires sources ont été remplacées par `[email retiré]`.

## Provenance et reproduction

- Extraction RFE/SFAR : notebook `dataset_extraction_has_sfar.ipynb` du dépôt `bayesimpact/notebooks`, dossier `HAS/`.
- Évaluation associée : `evaluation_llm_has_sfar.ipynb`, même dossier (closed-book contre recommandation complète fournie).
- Droits d'usage : la SFAR a confirmé en juillet 2026 que ses recommandations peuvent être librement travaillées ; les recommandations HAS sont des documents publics. Ne jamais intégrer une version éditeur (Elsevier, Springer…) portant une mention de droits réservés : utiliser la version publiée sur le site de la société savante.

## Licence

CC BY-SA 4.0, comme les autres corpus de ce dépôt (voir `LICENCE.md`). Les textes des recommandations restent la propriété de leurs auteurs (HAS, SFAR et sociétés associées).
