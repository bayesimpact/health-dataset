[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20851800.svg)](https://doi.org/10.5281/zenodo.20851800)

## **🇫🇷 Format des fichiers (OKF v0.1)**

Chaque document du corpus est un fichier Markdown avec un frontmatter YAML standardisé :

```yaml
type: resource   # ou template
title: "..."
description: "..."
tags: [tag1, tag2]
timestamp: YYYY-MM-DD
```

Valeurs de `type` :
* `resource` — fiche clinique de référence, contenu stable.
* `template` — modèle à personnaliser par centre (contient des variables `{{NOM_VARIABLE}}`).

## **🇬🇧 File format (OKF v0.1)**

Each document in the corpus is a Markdown file with a standardized YAML frontmatter:

```yaml
type: resource   # or template
title: "..."
description: "..."
tags: [tag1, tag2]
timestamp: YYYY-MM-DD
```

Values for `type`:
* `resource` — stable clinical reference document.
* `template` — model to be customized per center (contains `{{VARIABLE_NAME}}` placeholders).

---

## **🇫🇷 Mention légale (Attribution)**

Ce corpus d’information et d’éducation thérapeutique des patients transplantés hépatiques a été initié par Elise Goyon et le Pr Eric Vibert, avec le soutien du Pr Audrey Coilly.

Il a été coréalisé par l’équipe soignante du Centre Hépato-Biliaire Henri Bismuth (Elise Goyon, Alexandra Kokar, Nolwen Leost, Dylan Tisserand, Adeline Preiss, Zohra Abaoud et Thomas Bréard), à l’Hôpital Paul-Brousse, AP-HP (Assistance Publique – Hôpitaux de Paris).

La diffusion de cette œuvre est soumise à la licence **Creative Commons Attribution – Partage dans les Mêmes Conditions 4.0 International (CC-BY-SA 4.0)**.

## **🇬🇧 Legal notice (Attribution)**

This corpus of information and therapeutic education for liver transplant patients was initiated by Elise Goyon and Prof. Eric Vibert, with support from Prof. Audrey Coilly.

It was co-developed by the care team of the Henri Bismuth Hepato-Biliary Center (Elise Goyon, Alexandra Kokar, Nolwen Leost, Dylan Tisserand, Adeline Preiss, Zohra Abaoud and Thomas Bréard) at Hôpital Paul-Brousse, AP-HP (Assistance Publique – Hôpitaux de Paris).

This work is distributed under the **Creative Commons Attribution – ShareAlike 4.0 International license (CC BY-SA 4.0)**.

---

## **🇫🇷 Remerciements**

Ce projet a été réalisé grâce au soutien :

* de la [**Chaire BOpA**](https://www.chaire-bopa.fr/) (AP-HP / Université Paris-Saclay),  
* de l’association [**Bayes Impact France**](https://www.bayesimpact.org/), dont la plateforme open source a été utilisée pour créer l’assistant conversationnel et y tester le corpus,  
* et de l’association de patients [**Transhépate**](https://www.transhepate.org/), dont les patients experts ont contribué par leurs tests et retours.

## **🇬🇧 Acknowledgements**

This project was made possible thanks to the support of:

* [**BOpA Chair**](https://www.chaire-bopa.fr/) (AP-HP / Université Paris-Saclay),  
* [**Bayes Impact France**](https://www.bayesimpact.org/) association, whose open-source platform was used to build the conversational assistant and test the corpus,  
* and [**Transhépate**](https://www.transhepate.org/) patient association, whose expert patients contributed through testing and feedback.

---

## **🇫🇷 Comment citer**

Si vous réutilisez ce corpus, merci de le citer. Citation suggérée :

> Goyon, E. *et al.* (Centre Hépato-Biliaire Henri Bismuth, AP-HP). *Corpus Colette — éducation thérapeutique des patients transplantés hépatiques*. 2026. Version 26.06.0. https://doi.org/10.5281/zenodo.20851800

Le bouton **« Cite this repository »** dans la barre latérale droite de GitHub (alimenté par le fichier [`CITATION.cff`](CITATION.cff)) vous permet d'exporter la citation complète (incluant tous les co-auteurs dans le bon ordre) au format APA ou BibTeX.

---

## **🇬🇧 How to cite**

If you reuse this corpus, please cite it. Suggested citation:

> Goyon, E. *et al.* (Henri Bismuth Hepato-Biliary Center, AP-HP). *Colette Corpus — Therapeutic Patient Education for Liver Transplant Recipients*. 2026. Version 26.06.0. https://doi.org/10.5281/zenodo.20851800

GitHub's **"Cite this repository"** button in the right sidebar (powered by [`CITATION.cff`](CITATION.cff)) exports a ready-to-use citation (including all co-authors in the correct order) in APA or BibTeX format.
