# World Generation and Geography

**Status:** Approved baseline

## World structure

The world is one planet containing continents, oceans, regions, settlements and a two-dimensional grid of plots. Continents are generated as parts of one coherent planet. Only selected areas need to be accessible at launch.

The generation order is causal:

1. deterministic world seed and planet parameters
2. continental forms and ocean basins
3. tectonic and broad geological structures
4. elevation, mountains, valleys and drainage
5. climate zones, rainfall and temperature
6. rivers, lakes, coasts and groundwater potential
7. soils and biomes
8. connected deposits and renewable-resource potential
9. regions, settlements and initial infrastructure
10. plot materialisation

Plot values must be derived from these layers, not independently randomised.

## Lazy materialisation

The generator may know a plot deterministically before a full database row exists. A plot is materialised when it becomes accessible, is observed, owned, modified or needed by simulation. Materialisation must always reproduce the same untouched state from the world seed and generator version.

Generated facts that ownership or exploration can depend upon must never silently change after release. Generator migrations require an explicit compatibility plan.

## Expansion

Opening a continent changes accessibility, not planetary history. Closed areas may be:

- inaccessible and coarsely simulated
- NPC-maintained at a regional aggregate level
- revealed through an in-world discovery or policy event

Expansion criteria may include population density, land scarcity, economic health and operational capacity. Exact thresholds are balance configuration.

## Geography and movement

Plots have coordinates, elevation, terrain, passability and adjacency. Water, cliffs, protected land and missing infrastructure may block or penalise movement. Roads, rail, ports and airports create route edges with different speed, capacity and cost.

Use real pathfinding over traversable edges for meaningful travel. Straight-line estimation is acceptable only for previews clearly labelled as estimates.

## Scale — open decision

Plot dimensions, continent count and maximum accessible plots remain undecided. They must be selected together using:

- expected plots needed per active player
- settlement density
- travel-time targets
- database and pathfinding benchmarks
- scarcity and property-market goals

Do not hard-code a plot size until a prototype demonstrates the trade-off.

