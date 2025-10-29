# Données BRVM

Ce repository contient les données boursières de la Bourse Régionale des Valeurs Mobilières (BRVM) mises à jour automatiquement.

## 📊 Structure des données

- **Tickers disponibles** : 47
- **Fichiers de données** : 235
- **Dernière release** : Aucune

Les données sont organisées par ticker et par période :

```
data/
├── ABJC/
│   ├── ABJC.daily.csv
│   ├── ABJC.weekly.csv
│   ├── ABJC.monthly.csv
│   ├── ABJC.quarterly.csv
│   └── ABJC.yearly.csv
├── ONTBF/
│   └── ...
└── ...
```

## 🔄 Mise à jour

Les données sont mises à jour automatiquement :
- ⏰ Toutes les 15 minutes pendant les heures de trading
- 📅 Du lundi au vendredi
- 🕗 De 8h30 à 17h00 UTC

## 📈 Format des données

Chaque fichier CSV contient :
- **Date** : Date de la donnée (YYYY-MM-DD)
- **Open** : Prix d'ouverture
- **High** : Prix le plus haut
- **Low** : Prix le plus bas
- **Close** : Prix de clôture
- **Volume** : Volume échangé

## 🌐 Utilisation

```javascript
const fetchTickerData = async (ticker, period = 'daily') => {
  const response = await fetch(
    `https://raw.githubusercontent.com/Fredysessie/brvm-data-public/main/data/${ticker}/${ticker}.${period}.csv`
  );
  return await response.text();
};
```

## 📦 Releases

Des archives de toutes les données sont disponibles dans les [Releases](https://github.com/Fredysessie/brvm-data-public/releases).

---
*Dernière mise à jour: 2025-10-29 11:31 UTC*
