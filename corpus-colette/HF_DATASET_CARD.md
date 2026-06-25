---
license: cc-by-sa-4.0
language:
  - fr
task_categories:
  - question-answering
  - text-generation
task_ids:
  - extractive-qa
tags:
  - medical
  - patient-education
  - liver-transplantation
  - hepatology
  - RAG
  - French
pretty_name: Colette Corpus — ETP transplantation hépatique
size_categories:
  - n<1K
---

# Colette Corpus — Therapeutic Patient Education for Liver Transplant Recipients

Corpus d'information et d'éducation thérapeutique des patients (ETP) transplantés hépatiques, développé par l'équipe soignante du Centre Hépato-Biliaire Henri Bismuth (Hôpital Paul-Brousse, AP-HP, Villejuif).

Ce corpus a été conçu pour alimenter un assistant conversationnel destiné aux patients en liste d'attente ou en suivi post-greffe. Il couvre les questions fréquentes, les médicaments immunosuppresseurs, l'alimentation, la cicatrisation et les protocoles de suivi.

## Contenu

Le corpus contient deux types de documents :

- `resource` — fiches cliniques de référence (contenu stable, validé par l'équipe médicale) : FAQ, guide de la transplantation, médicaments, conseils alimentaires, cicatrice.
- `template` — modèles à personnaliser par centre (variables `{{NOM_VARIABLE}}`) : fiche de contact équipe, protocole de suivi en liste d'attente.

Chaque fichier suit le format **OKF v0.1** : un frontmatter YAML standardisé (`type`, `title`, `description`, `tags`, `timestamp`) sur chaque fichier Markdown.

## Utilisation

```python
from datasets import load_dataset

dataset = load_dataset("bayesimpact/colette-etp-corpus-fr", split="train")
```

Ce corpus est adapté à des usages de type RAG (Retrieval-Augmented Generation) pour des assistants patients, ou à l'évaluation de LLM sur des textes médicaux en français.

## Périmètre et limites

Ce corpus contient exclusivement des contenus d'ETP rédigés par des soignants. Il ne contient pas de données patients, de logs de conversations ni de conseils d'urgence. Il ne doit pas être utilisé pour du diagnostic médical. Tout déploiement dans un contexte clinique nécessite une validation médicale locale.

## Auteurs

Elise Goyon, Alexandra Kokar, Nolwen Leost, Dylan Tisserand, Adeline Preiss, Zohra Abaoud, Thomas Bréard, Audrey Coilly, Eric Vibert — Centre Hépato-Biliaire Henri Bismuth, Hôpital Paul-Brousse, Assistance Publique - Hôpitaux de Paris (AP-HP), Villejuif, France.

## Citation

```bibtex
@dataset{colette_corpus_2026,
  author    = {Goyon, Elise and Kokar, Alexandra and Leost, Nolwen and Tisserand, Dylan and Preiss, Adeline and Abaoud, Zohra and Bréard, Thomas and Coilly, Audrey and Vibert, Eric},
  title     = {Colette Corpus — Therapeutic Patient Education for Liver Transplant Recipients},
  year      = {2026},
  version   = {26.06.0},
  doi       = {10.5281/zenodo.20851800},
  url       = {https://doi.org/10.5281/zenodo.20851800}
}
```

DOI Zenodo : [10.5281/zenodo.20851800](https://doi.org/10.5281/zenodo.20851800)
Source GitHub : [bayesimpact/health-dataset](https://github.com/bayesimpact/health-dataset/tree/main/corpus-colette)

## Licence

Corpus : [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
Scripts : MIT

## Remerciements

Ce projet a été réalisé avec le soutien de la [Chaire BOpA](https://www.chaire-bopa.fr/) (AP-HP / Université Paris-Saclay), de l'association [Bayes Impact France](https://www.bayesimpact.org/) dont la plateforme open source a été utilisée pour créer l'assistant conversationnel, et de l'association de patients [Transhépate](https://www.transhepate.org/).
