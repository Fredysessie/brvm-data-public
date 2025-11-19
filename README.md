# Données BRVM

Ce repository contient les données boursières de la Bourse Régionale des Valeurs Mobilières (BRVM) mises à jour automatiquement.

## 📊 Structure des données

- **Tickers disponibles** : 66
- **Fichiers de données** : 398
- **Devises suivies** : 52
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
├── currency_data/
│   ├── XOF.json
│   ├── EUR.json
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

Les fichiers de devises (JSON) contiennent les taux de change sur 3 mois.

## 🌐 Utilisation

```javascript
const fetchTickerData = async (ticker, period = 'daily') => {
  const response = await fetch(
    `https://raw.githubusercontent.com/Fredysessie/brvm-data-public/main/data/${ticker}/${ticker}.${period}.csv`
  );
  return await response.text();
};

const fetchCurrencyData = async (currencyCode) => {
  const response = await fetch(
    `https://raw.githubusercontent.com/Fredysessie/brvm-data-public/main/data/currency_data/${currencyCode}.json`
  );
  return await response.json();
};
```

## 📦 Releases

Des archives de toutes les données sont disponibles dans les [Releases](https://github.com/Fredysessie/brvm-data-public/releases).

---
*Dernière mise à jour: 2025-11-19 09:24 UTC*
