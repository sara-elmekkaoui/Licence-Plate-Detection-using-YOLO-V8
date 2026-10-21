# Détection et reconnaissance des plaques d’immatriculation marocaines

## Présentation

Ce projet consiste à développer un système de reconnaissance automatique des plaques d’immatriculation (ANPR — *Automatic Number Plate Recognition*) appliqué aux véhicules marocains.

Le système combine la détection des plaques par YOLOv8 et la reconnaissance optique de caractères (OCR) afin de localiser les plaques dans les images ou les vidéos et d’extraire les caractères qui y figurent.

## Fonctionnalités

- Détection des plaques d’immatriculation.
- Reconnaissance des caractères des plaques par OCR.
- Traitement d’images et de vidéos.
- Gestion de l’affichage du texte arabe.
- Visualisation des résultats de détection et de reconnaissance.
- Interface interactive avec Streamlit, si utilisée dans `main.py`.

## Technologies utilisées

Python : langage de programmation.

YOLOv8 : détection des plaques d’immatriculation.

Ultralytics : implémentation du modèle YOLO.

PyTorch : framework de Deep Learning.

OpenCV : traitement d’images et de vidéos.

Pytesseract : reconnaissance optique de caractères.

Streamlit : création de l’interface web interactive.

NumPy et Pillow : manipulation et traitement des images.

Arabic Reshaper et Python-Bidi : mise en forme et affichage du texte arabe.

## Structure du projet

```text
ANPR/
├── captured_plates/       # Plaques capturées
├── LPR.v2i.yolov8/        # Dataset : entraînement, validation et test
│   ├── train/
│   ├── valid/
│   ├── test/
│   └── data.yaml
├── rapport de stage/      # Rapport du projet
├── bestdetecet.pt         # Poids du modèle de détection
├── bestocr.pt             # Poids du modèle OCR, selon son usage
├── Lateef-Medium.ttf      # Police pour l’affichage du texte arabe
├── main.py                # Application principale
├── ocr.py                 # Traitement OCR
├── requirements.txt       # Dépendances Python
└── README.md              # Documentation du projet
```

## Installation

### 1. Cloner le dépôt

```bash
git clone https://github.com/sara-elmekkaoui/Licence-Plate-Detection-using-YOLO-V8.git
cd Licence-Plate-Detection-using-YOLO-V8
```

### 2. Créer un environnement virtuel

```bash
python -m venv .venv
```

Sous Windows, activer l’environnement :

```powershell
.\.venv\Scripts\Activate.ps1
```

### 3. Installer les dépendances

```bash
python -m pip install -r requirements.txt
```

### 4. Vérifier les fichiers nécessaires

Vérifier que les fichiers de poids `.pt` sont présents et que les chemins utilisés dans les scripts Python correspondent à leur emplacement.

Si le projet utilise Tesseract OCR, installer également le moteur Tesseract sur le système.

## Exécution

Si `main.py` utilise Streamlit :

```bash
streamlit run main.py
```

Pour exécuter directement le script OCR :

```bash
python ocr.py
```

Les commandes doivent être adaptées selon le fonctionnement réel des scripts.

## Dataset

Le dossier `LPR.v2i.yolov8` contient les données organisées en ensembles d’entraînement, de validation et de test. Le fichier `data.yaml` définit normalement les chemins et les classes du dataset utilisé pour la détection.

## Applications possibles

- Reconnaissance automatique des plaques d’immatriculation.
- Identification de véhicules.
- Gestion intelligente des parkings.
- Surveillance et analyse du trafic routier.
- Applications de vision par ordinateur.

## Perspectives d’amélioration

- Améliorer la précision de la reconnaissance des caractères.
- Évaluer les performances sur des images prises dans différentes conditions.
- Optimiser le traitement vidéo.
- Améliorer la robustesse face aux variations d’éclairage et aux plaques partiellement masquées.
- Développer une interface de démonstration plus complète.
