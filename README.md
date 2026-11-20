# Prédiction du taux de clic (CTR) pour la publicité en ligne

Notebook unique : `ctr_prediction.ipynb`.

Prédiction de la probabilité de clic sur le jeu public de Criteo (*Display Advertising Challenge*), avec un découpage chronologique. Comparaison d'une régression logistique avec *hashing trick*, de LightGBM et d'un réseau **DeepFM** (PyTorch), évalués par log loss, AUC, *Normalized Entropy* et calibration. Section optionnelle PySpark pour le passage à l'échelle.

## Lancer

1. Télécharger les données (voir `data/README.md`) ou décommenter la cellule de téléchargement du notebook.
2. `pip install -r requirements.txt` puis exécuter le notebook (ou l'ouvrir dans Google Colab).

## Résultats

<!-- Coller ici le tableau de la section 7 du notebook. -->
