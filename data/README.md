# Données

Placer ici `train.txt` (jeu Criteo *Display Advertising Challenge*).

Téléchargement (~4 Go compressé), puis on garde le premier million de lignes :

```bash
wget -O dac.tar.gz https://ndownloader.figshare.com/files/10082655
tar -xzOf dac.tar.gz train.txt | head -n 1000000 > data/train.txt
```

Les données ne sont pas versionnées (taille, conditions d'utilisation de Criteo Labs).
