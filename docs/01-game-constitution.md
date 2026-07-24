# Project Society — Game Constitution

**Status:** Approved baseline  
**Authority:** This is the highest product-design authority below explicit owner decisions and approved decision records.

## Purpose

Project Society is one persistent society simulation. It has no universal victory condition. Players choose their own ambitions and participate in a world that continues without them.

## Constitutional laws

1. **Players define success.** Wealth, mastery, service, influence, stability, crime, research and community are equally valid directions.
2. **The world persists.** A normal release never resets history, ownership or the economy. Expansion opens more of the same planet.
3. **Systems cause gameplay.** Features must follow from world rules and connect to other systems.
4. **Depth must not become clerical work.** Taxes, accounting, payroll and routine billing are automatic. Players make decisions.
5. **Interesting consequences outrank literal realism.** Abstract details that do not create choices, while preserving their strategic effects.
6. **Quality propagates.** Inputs, skill, equipment, facility, method and handling influence output quality and durability.
7. **Provenance matters.** Important resources, products, buildings, research and ownership changes remain traceable.
8. **Information is earned.** Database existence does not imply player visibility.
9. **Players outperform NPCs.** NPCs provide minimum continuity, have capped competence and yield roles gracefully.
10. **Rules precede AI.** NPCs use deterministic policies by default. AI may choose only among validated, auditable game commands.
11. **Server time is authoritative.** Clients never award completion, money, goods, XP or movement.
12. **Finite resources stay finite.** Minerals, oil and gas deplete. Renewable resources recover only under suitable conditions.
13. **Failure is real.** Companies, banks, governments, crops, projects and criminal plans can fail.
14. **No pay-to-win economy.** World currency, skills, resources and political power cannot be bought for real money.
15. **One account has one active character.** Alternate-character economic self-dealing is not a supported play style.
16. **The official client and API obey identical rules.**
17. **No global per-entity ticking.** Store aggregate state and resolve detail on actions, events and bounded scheduled updates.

## Player dignity and proportional loss

Consequences must matter without making months of participation meaningless. Character death, imprisonment, bankruptcy and repossession may cause substantial loss, delay or reduced control, but do not delete the account or arbitrarily erase unrelated mastery.

New players receive clear risk communication and a bounded introduction. They are not permanently immune.

## Constitutional test for a feature

A proposed feature must answer:

- What meaningful decision does it create?
- Which existing systems cause and consume it?
- What information may each actor know?
- Can it be computed without continuous global ticking?
- What abuse or economic exploit does it enable?
- Can NPCs maintain a minimum version without dominating players?
- Can it begin as a small vertical slice?

If the feature only adds repetitive administration, it is rejected or automated.

## Amendment process

Changes require an explicit owner decision. Record amendments in Git and, when the consequence is broad or difficult to reverse, in `/decisions`. Domain documents may refine this constitution but never contradict it.

