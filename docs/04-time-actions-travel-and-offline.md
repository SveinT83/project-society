# Time, Actions, Travel and Offline Behaviour

**Status:** Approved baseline

## Time model

Calendar time follows real time: one real day is one world day. Individual processes use compressed durations chosen for playable pacing.

All timers use server-authoritative timestamps. An action normally has `started_at`, `completes_at`, status, inputs reserved, actor, location and an idempotent completion key.

## Personal actions

A character may start a valid action when requirements are met. Logging out does not cancel it. At completion, the server resolves the result exactly once. The character does not automatically start another personal action unless a later, explicitly approved automation system permits it.

Action speed may depend on:

- relevant skill
- education or researched method
- character energy, health and temporary effects
- equipment quality and suitability
- facility quality
- terrain, weather and infrastructure

Bonuses require caps and diminishing returns so durations never reach zero.

## Parallel activity

The character cannot perform incompatible physical actions simultaneously. Limited remote administration may be possible while travelling or performing passive activities when technology and domain rules allow it.

## Travel

Travel is an action along an authoritative route. Walking, road vehicles, trains, boats and aircraft have distinct networks and requirements.

The route engine considers:

- traversability and legal access
- terrain and slope
- roads and road class
- rail, ports, airports and schedules
- vehicle capability, fuel and condition
- congestion and exceptional closures

Better footwear may improve walking modestly. Vehicles and infrastructure provide the main long-distance advantage.

## Offline needs and danger

Hunger, thirst and ordinary energy decay are frozen while the player is offline after the current personal action resolves. This prevents absence from becoming a death sentence.

The character remains at the last authoritative location and is not universally immune. World events and hostile actions may affect that location, subject to proportional-loss and anti-griefing rules.

## Business continuity

Facilities, contracted NPC work, already-scheduled production, crops, utilities, interest and government systems may continue independently of owner login. Personal actions and organisation operations are separate concepts.

