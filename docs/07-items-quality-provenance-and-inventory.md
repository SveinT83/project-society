# Items, Quality, Provenance and Inventory

**Status:** Approved baseline

## Item model

Items exist as traceable units or homogeneous batches. Use individual identity for durable, owned or uniquely modified objects; use batches for fungible materials with the same type, grade, provenance summary and location.

Inventory is always attached to an actor, container, building, vehicle or plot location. Transfers are transactional and conserve quantity.

## Quality

Quality is not a single arbitrary bonus. Each product type declares relevant dimensions such as purity, durability, precision, nutrition or safety. A derived display score may summarise these dimensions.

Transformation uses:

- input qualities and quantities
- worker skill and condition
- tool and facility quality
- selected method or recipe
- researched improvements
- handling, storage and process variance

No process creates unexplained quality from nothing. Exceptional skill may reduce loss and realise more of the inputs' potential.

## Provenance

Every output points to its production event. The event references input batches, actors, facility, recipe/method and time. This forms a provenance graph.

User interfaces may show a compact history; audits and recalls can traverse deeper history. Retain provenance efficiently through immutable events and batch lineage rather than copying complete histories.

## Durability

Durable goods have condition and expected wear behaviour. Use, environment, maintenance, misuse and initial quality affect wear. Broken goods may be repaired, dismantled or recycled.

## Storage

Storage has capacity, access control and environmental suitability. Poor storage may reduce quality or increase loss for perishable and sensitive goods. Reserve inputs when a timed process starts so they cannot be double-spent.

