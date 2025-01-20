# Document Q&A Bot

Ce projet implémente un chatbot avancé de questions-réponses sur des documents en utilisant des modèles de langage de grande taille et la méthodologie Retrieval-Augmented Generation (RAG).

---

## Table des Matières
1. [Description du Projet](#description-du-projet)
2. [Fonctionnalités Clés](#fonctionnalités-clés)
3. [Prérequis](#prérequis)
4. [Installation](#installation)
5. [Démarrage](#démarrage)
6. [Technologies Utilisées](#technologies-utilisées)
7. [Architecture](#architecture)
8. [Utilisation](#utilisation)
9. [Démo Vidéo](#démo-vidéo)
10. [Contributeurs](#contributeurs)

---

## Description du Projet
Ce chatbot a pour objectif de fournir des réponses précises et contextuelles à partir de documents volumineux (PDF, DOCX, TXT). Il repose sur des techniques avancées de traitement du langage naturel (NLP) et permet de récupérer les informations pertinentes tout en indiquant leur source dans le document.

## Fonctionnalités Clés
- Support des formats de documents PDF, DOCX et TXT.
- Recherche sémantique basée sur les embeddings vectoriels.
- Génération de réponses contextuelles et transparentes.
- Interface utilisateur intuitive créée avec Streamlit.

## Prérequis
- Python 3.8 ou supérieur.
- Clé API Hugging Face (pour les modèles de langage).
- Docker (optionnel pour la conteneurisation).

## Installation

1. Clonez le dépôt :
   ```bash
   git clone https://github.com/votre-dépôt.git
   cd votre-dépôt
   ```

2. Installez les dépendances Python :
   ```bash
   pip install -r requirements.txt
   ```

3. Configurez les variables d’environnement en créant un fichier `.env` :
   ```env
   HF_TOKEN=VotreTokenHuggingFace
   ```

## Démarrage

1. Lancez l’application Streamlit :
   ```bash
   streamlit run app.py
   ```

2. Accédez à l’interface utilisateur dans votre navigateur :
   ```
   http://localhost:8501
   ```

## Technologies Utilisées

- **LangChain** : Orchestration du traitement NLP.
- **FAISS** : Recherche vectorielle rapide.
- **Hugging Face Transformers** : Modèles de langage pour embeddings et génération.
- **Streamlit** : Interface utilisateur.
- **Docker** : Conteneurisation et déploiement.

## Architecture
L’application Document Q&A Bot repose sur la méthodologie Retrieval-Augmented Generation (RAG) pour améliorer la précision et la pertinence des réponses générées. Cette approche combine des techniques avancées de récupération d’informations avec la génération de texte, assurant ainsi que les réponses fournies sont non seulement contextuelles, mais également basées sur des informations extraites directement des documents téléchargés par l’utilisateur.

### Illustration de l'Architecture

![image](https://github.com/user-attachments/assets/9e7a2595-398a-4f57-bada-360e8eed5862)


Le processus commence par l’extraction du contenu du document, qu’il s’agisse de fichiers PDF, DOCX, ou TXT. Ce contenu est ensuite divisé en segments plus petits (également appelés chunks) à l’aide de RecursiveCharacterTextSplitter, ce qui permet de structurer les données pour un traitement plus efficace. Chaque segment de texte est transformé en un vecteur d’embedding à l’aide du modèle sentence-transformers/all-MiniLM-L6-v2. Ce modèle est conçu pour capturer le sens et le contexte du texte sous une forme numérique, facilitant ainsi la comparaison entre les différents segments de texte.

Ces embeddings sont ensuite indexés dans une base de données vectorielle à l’aide de FAISS (Facebook AI Similarity Search), une technologie qui permet d’effectuer des recherches de similarité extrêmement rapides et efficaces parmi des ensembles de données volumineux. Cette étape est cruciale, car elle prépare le terrain pour la récupération rapide des segments les plus pertinents lorsque l’utilisateur pose une question.

Lorsqu’une question est soumise par l’utilisateur, celle-ci est convertie en embedding de requête en utilisant le même modèle sentence-transformers/all-MiniLM-L6-v2. Une recherche sémantique est ensuite effectuée dans l’index FAISS pour identifier les segments de texte les plus pertinents par rapport à la question posée. Ces segments récupérés fournissent le contexte nécessaire pour la génération de la réponse.

La génération de la réponse est réalisée par le modèle mistralai/Mistral-7B-Instruct-v0.1, un modèle de langage génératif capable de produire des réponses cohérentes et précises en fonction du contexte fourni. Le modèle prend les segments récupérés et la question de l’utilisateur pour générer une réponse qui est à la fois contextuellement adaptée et basée sur des informations exactes extraites du document original.

## Utilisation
1. **Uploader un Document** : Cliquez sur "Browse files" pour charger un fichier.
2. **Poser une Question** : Entrez une question sur le contenu du document.
3. **Afficher les Résultats** : Consultez la réponse et sa source dans le document.

## Démo Vidéo
Pour une démonstration complète du fonctionnement de l'application, consultez la vidéo suivante :
https://github.com/user-attachments/assets/033d12e3-6116-4afb-85a8-89d2fbd8985e
![Démo GIF](https://github.com/user-attachments/assets/033d12e3-6116-4afb-85a8-89d2fbd8985e)
<video controls width="100%">
  <source src="https://github.com/user-attachments/assets/033d12e3-6116-4afb-85a8-89d2fbd8985e" type="video/mp4">
  Votre navigateur ne supporte pas les vidéos.
</video>


## Contributeurs
- BELAHRECH Abderrahmane
- Dalil Ali
- FATHALLAH Oussama
- BENLAMRABET Abdelwadoud

Encadré par :
- M. Aissam Outchakoucht

---

**Année Universitaire :** 2024/2025

