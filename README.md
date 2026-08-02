# GOC Darkmoon Calculator — Frostheim VS Darkmoon

A standalone web app for the **Darkmoon** battle-station season. Pick a **Darkmoon defender** and a **Frostheim attacker** and instantly get:

- the exact **debuff %** you need,
- the **KOs** and **fodder** required to defeat the defender,
- the element matchup (×1.2 advantage / ×0.8 disadvantage),

plus every member's **identified character cards** matched to the official
[Tokyo Debunker List of Character Cards](https://tokyodebunker.miraheze.org/wiki/List_of_Character_Cards)
and rated with the **Tokyo Debunker Full Data** system — Case Tier (A/B/C/D), ATK grade (P/S), and True Speed (TU = ⌊(1000 − Speed) ÷ 10⌋).

## Data source

Rosters are extracted from the **Darkmoon** and **Frostheim** sheets of the
updated `my GOC Stats (4).xlsx` workbook (rebuild with `data/build_darkmoon_data.py`).

## Keeping it fresh

Use the **⬆ Import from Excel** button to drop in an updated workbook — the
Darkmoon & Frostheim sheets load with all characters re-matched and saved
locally in your browser (no re-publish needed).

## KO math

```
debuff = ⌈ max(0, 1 − (attacker power × element multiplier) ÷ defender power) ⌉  (rounded up to nearest 5%)
KOs    = debuff × 480
fodder = KOs ÷ 6
```

Identical to the spreadsheet's AC4:AE table.

## Live site

https://t12-a.github.io/goc-darkmoon-calculator/
