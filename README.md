# Menu Intelligence Dataset Registry

We're building the definitive structured dataset of restaurant menus in New York City — and eventually, every major metro in the US.

Since December 2025, our system has been continuously collecting, structuring, and analyzing menus across hundreds of NYC restaurants. We don't just capture what's on a menu today. We capture how menus change — what dishes appear, what disappears, how prices move, and what patterns emerge across neighborhoods, cuisines, and seasons.

This is the kind of longitudinal food data that has never existed at this level of detail.

## What's in the Dataset

**Hundreds of restaurants.** Tens of thousands of dishes and beverages. Every item structured with pricing, categorization, and ingredients — linked across restaurants so you can compare the same dish city-wide.

**Monthly snapshots.** We capture menus at regular intervals, building a living history of NYC's dining landscape. Which restaurants are raising prices? Which dishes are trending? What's seasonal and what's permanent?

**Allergen intelligence.** Confidence-scored allergen profiles for menu items, built to power the next generation of dietary safety tools.

## Dataset Growth

| Period | Restaurants | Menu Items | Snapshots |
|--------|------------|------------|-----------|
| Dec 2025 | 18 | 1,570 | 27 |
| Jan 2026 | 109 | 19,796 | 285 |
| Feb 2026 | 181 | 31,113 | 409 |

This repo is updated monthly with a new entry as the dataset grows.

## Data Integrity

Each month, the complete dataset is hashed (SHA-256) and the hash is committed here. The data itself is private — only aggregate counts and the cryptographic fingerprint are published.

The git commit timestamps serve as an immutable public record of the dataset's existence and scale at each point in time. Given access to the raw dataset, anyone can independently verify a proof by computing the hash and comparing it to the value in `proofs/YYYY-MM.json`.

## Contact

Restaurant owners can request removal by [opening an issue](https://github.com/lifesized/menu-data-proofs/issues) in this repository.
