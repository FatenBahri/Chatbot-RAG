# Chatbot-RAG

Projet de démonstration d'un chatbot à base de RAG (Retrieval-Augmented Generation).

**Description**

Ce dépôt contient des ressources et des notebooks pour construire un assistant conversationnel qui combine récupération d'informations (vector store) et génération de texte. Le projet illustre le flux : ingestion de documents → création d'embeddings → indexation vectorielle → requêtage + génération.

**Structure du dépôt**

- `data/` : jeux de textes sources utilisés pour l'indexation.
- `notebook/` : notebooks Jupyter (ex. `bot.ipynb`, `prototypage.ipynb`) pour prototyper et exécuter le pipeline.
- `pgvector/` : sources et utilitaires liés à `pgvector` (optionnel si vous utilisez PostgreSQL + extension pgvector).
- `src/` : code source (scripts et helpers).
- `requirements.txt` : Dépendances Python du projet. 

**Prérequis**

- Python 3.10+ (ou 3.8+ selon les dépendances listées).
- `pip` pour installer les dépendances.
- Optionnel : PostgreSQL + extension `pgvector` si vous souhaitez utiliser une base de vecteurs locale.

**Installation**

1. Créez et activez un environnement virtuel :

```bash
python -m venv .venv
.venv\Scripts\Activate.ps1 # (Windows)
```

2. Installez les dépendances :

```bash
pip install -r requirements.txt
```

**Préparation des données**

Placez vos documents texte dans le dossier `data/`. Les notebooks fournis montrent comment :

- charger les fichiers
- segmenter le texte
- calculer les embeddings
- indexer les vecteurs dans la base (ou un store local)

**Exécution rapide**

1. Ouvrez le notebook principal :

```bash
jupyter notebook
```

2. Ouvrez [notebook/bot.ipynb](notebook/bot.ipynb) et suivez les cellules pour construire l'index et lancer des requêtes.

**Notes d'utilisation**

- Si vous utilisez une API externe pour les embeddings ou la génération (ex. OpenAI), configurez vos clés d'API dans des variables d'environnement avant d'exécuter les notebooks.
- Si vous optez pour PostgreSQL + `pgvector`, consultez le dossier `pgvector/` et installez l'extension côté serveur.
	- Note : j'ai lancé PostgreSQL via WSL (Windows Subsystem for Linux) pour tester le backend vectoriel sur cette machine. (configuration et installation de pgvector sous wsl sur la port 5433)

**Contribuer**

Suggestions de contributions : améliorer les notebooks, ajouter des scripts CLI pour l'ingestion, supporter d'autres backends vectoriels.

**Licence**

Vérifiez la présence d'un fichier `LICENSE` dans le dépôt pour les informations de licence. Si absent, contactez l'auteur du projet pour précisions.

---

Si vous souhaitez, je peux :
- ajouter des exemples de commandes pour ingérer les fichiers du dossier `data/`
- créer un script `scripts/ingest.py` pour automatiser l'ingestion
- ou préparer un petit guide pas-à-pas pour déployer une instance PostgreSQL + `pgvector`.

