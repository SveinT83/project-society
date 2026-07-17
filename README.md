# Project Society

## Vision

Project Society is a persistent online society simulator where players shape a living world through work, trade, ownership, politics, research, cooperation, crime and competition.

There is no predefined end goal. Every player creates their own purpose.

One player may aim to become the world's best farmer and produce grain of the highest possible quality. Another may build an industrial group, work as an employee, become a researcher, speculate in property, run a bank, lead a municipality, organise a political movement or pursue a criminal career.

The world continues to exist and develop whether individual players are online or offline.

> Project Society simulates a living world. Gameplay emerges from the interaction between its systems.

## What Project Society Is

Project Society is a persistent, browser-based society and economy simulator played primarily through a two-dimensional plot-based world map and contextual interfaces.

It combines elements of:

- society simulation
- player-driven economy
- production and logistics
- property ownership and development
- politics and public administration
- education and research
- crime, policing and justice
- persistent online world simulation

It is not built around a final victory condition, character levels or a scripted campaign.

## Core Design Principles

### Players define their own goals

The simulator does not tell players what success means. Wealth, skill, influence, craftsmanship, public service, ownership, research and social status are all valid ambitions.

### The world never stops

The world continues to evolve while players are offline. Active actions may complete, companies and automated production may continue, loans accrue interest, crops grow and public systems operate.

An offline player does not automatically begin new personal actions, but the world does not pause around them.

### Deep simulation, simple interaction

The world may be complex internally, but players should not be forced to perform boring administration.

Taxes, accounting entries, payroll deductions and routine payments should normally be automated. Players make strategic decisions rather than perform bookkeeping.

### Interesting decisions over unnecessary realism

The simulator should preserve realistic causes and consequences while abstracting details that do not create meaningful choices.

### Quality propagates

Quality flows through production chains. Raw-material quality, worker skill, equipment, processes and intermediate products influence the final result, its performance and durability.

### Everything has provenance

Resources, products, buildings and other important objects should retain a traceable origin whenever practical.

### Information is a resource

Players only receive information their character could reasonably know through presence, recent observation, ownership, employees, friendships, public records or technology.

### Players are preferred over NPCs

NPCs keep the world functional when too few players fill essential roles. Rule-driven behaviour is preferred; constrained AI may be used where necessary.

NPC skill is capped so committed players can surpass them.

### World state before continuous simulation

The system stores aggregated state and potential. Detailed outcomes are calculated when actions, events or scheduled regional updates require them. The simulator must not continuously model every tree, fish or animal.

## World Overview

The world consists of one persistent planet divided into plots, regions, continents and oceans.

Continents may exist from the beginning while only selected continents are initially accessible. More areas can be opened as the player population grows.

World generation must create coherent geography and geology before assigning plot-level details. Mountains, soils, climate, forests, mineral deposits, oil fields and other resources must form plausible connected structures rather than unrelated random values per plot.

Every accessible plot has persistent database state.

## Player Experience

The primary interface combines:

- a two-dimensional world map
- clickable plots
- contextual information panels
- action menus
- economy, company, property and government interfaces
- an in-world mobile phone or computer interface for remote services

Some actions and information require physical presence on the relevant plot. Public information may be available remotely when the player owns suitable technology and connectivity.

## Technology Direction

The current intended stack is:

### Backend

- Laravel
- PostgreSQL
- Redis
- queue workers
- scheduled jobs
- event-driven domain communication

### Frontend

- Vue
- Inertia
- Tailwind CSS

### Integration

- a controlled public API
- real-time communication where useful
- support for external statistics, dashboards and permitted player automation

The API must never bypass game rules. All external actions must pass through the same validation and simulation services as the official interface.

## Development Strategy

Project Society will be designed before major implementation begins.

Documentation is the authoritative source of truth. Code must follow approved domain documentation and architectural decisions.

The initial repository phase focuses on:

1. game constitution
2. world and society design
3. domain specifications
4. technical architecture
5. data model
6. staged implementation roadmap

Production implementation should begin only when the relevant foundational documents are sufficiently complete.

## Long-Term Goal

Create one persistent world where society, economy, industry, politics and culture emerge naturally from interactions between players, NPCs and the simulated environment.

> The world exists with or without the player. The player chooses their place within it.
