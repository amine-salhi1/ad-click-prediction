# Prédiction du taux de clic (CTR) pour la publicité en ligne

Notebook unique : `ctr_prediction.ipynb`.

Prédiction de la probabilité de clic sur le jeu public de Criteo (*Display Advertising Challenge*), avec un découpage chronologique. Comparaison d'une régression logistique avec *hashing trick*, de LightGBM et d'un réseau **DeepFM** (PyTorch), évalués par log loss, AUC, *Normalized Entropy* et calibration. Section optionnelle PySpark pour le passage à l'échelle.

## Lancer

1. Télécharger les données (voir `data/README.md`) ou décommenter la cellule de téléchargement du notebook.
2. `pip install -r requirements.txt` puis exécuter le notebook (ou l'ouvrir dans Google Colab).

## Résultats
1 000 000 d'affichages, découpage chronologique 80/10/10, CTR moyen du test = 0,2503 (Colab, GPU T4).

| Modèle | Log loss | AUC | Normalized Entropy | Calibration | Temps |
|---|---|---|---|---|---|
| Régression logistique (hashing) | 0,4613 | 0,7813 | 0,820 | 1,014 | 230 s |
| LightGBM | 0,4587 | 0,7849 | 0,815 | 1,010 | 111 s |
| DeepFM (PyTorch) | 0,4585 | 0,7850 | 0,815 | 1,028 | 11 s (GPU) |

- Les trois modèles réduisent la log loss d'environ 18 % par rapport au prédicteur constant (NE ≈ 0,82).
- LightGBM et DeepFM sont à égalité (écart d'AUC de 0,0001, dans le bruit) et devancent la régression logistique.
- DeepFM sur-apprend dès la 2e époque (early stopping à l'époque 1) ; LightGBM est le mieux calibré.
<!-- Coller ici le tableau de la section 7 du notebook. -->
