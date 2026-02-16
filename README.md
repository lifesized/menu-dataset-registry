# Menu Intelligence Dataset — Proof of Existence

Cryptographic proof that a comprehensive restaurant menu intelligence dataset has been continuously collected, structured, and maintained since **December 2025**.

## The Dataset

We're building the most detailed structured menu database in New York City. Every month, our system scrapes, extracts, and normalizes menu data across hundreds of restaurants — capturing not just what's on the menu, but how menus evolve over time.

**What we track:**

- **Restaurants** — Locations, neighborhoods, cuisine types, and pricing tiers across NYC
- **Dishes & Beverages** — Full menu items with prices, descriptions, ingredients, and category classifications
- **Menu Snapshots** — Point-in-time captures that reveal how menus change month over month
- **Dish Variant Groups** — Cross-restaurant analysis linking the same dish across different menus (e.g., every Margherita pizza in the city)
- **Allergen Verifications** — Confidence-scored allergen profiles with FDA-standard categorization
- **Historical Trends** — Price changes, seasonal rotations, dish additions and removals

## Growth

| Period | Restaurants | Dishes | Beverages | Snapshots |
|--------|------------|--------|-----------|-----------|
| Dec 2025 | 18 | 1,570 | — | 27 |
| Jan 2026 | 109 | 9,615 | 10,181 | 285 |
| Feb 2026 | 181 | 14,375 | 16,738 | 409 |

## Why This Repo Exists

Each month, the full dataset is exported as deterministic JSON and hashed with SHA-256. Only the hash and aggregate metadata are committed here — **the actual data remains private**.

The git commit history provides an immutable, publicly verifiable record that this data existed on or before each commit date. This is the same principle behind blockchain timestamping, but simpler.

## Proof Format

Each file in `proofs/` contains:

```json
{
  "version": "1.0",
  "period": "2026-02",
  "generatedAt": "2026-02-15T...",
  "hash": {
    "algorithm": "SHA-256",
    "value": "cf3cba3c..."
  },
  "metadata": {
    "restaurants": 181,
    "menuSnapshots": 409,
    "dishes": 14375,
    "beverages": 16738,
    "allergenVerifications": 0,
    "dishVariantGroups": 7243
  },
  "filter": {
    "type": "cumulative",
    "cutoffDate": "2026-03-01T00:00:00.000Z"
  },
  "note": null
}
```

## Verification

Given a dataset export for any period, anyone can verify it matches the proof:

```bash
# macOS
shasum -a 256 export.json

# Linux
sha256sum export.json
```

The hash must match the `hash.value` in the corresponding proof file. The export uses deterministic JSON serialization (sorted keys, ISO date strings) to ensure reproducibility.

## Notes

- Proofs marked with a `note` field were generated retroactively — the data existed at the stated time (verified by server-generated database timestamps), but the hash was committed after the fact.
- Starting February 2026, all proofs are generated contemporaneously.
- This repository contains **no actual data** — no restaurant names, menu items, prices, allergen profiles, or credentials.
