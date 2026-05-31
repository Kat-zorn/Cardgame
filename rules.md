# The idea behind Celestials (name WIP)

Note that any rules regarding card behavior outlined here
may be overwritten by the cards and phases themselves.
This will be explicitly mentioned.

## Players

There are two playable characters: `Sun` and `Moon`.
Each character has their own theme and with that, deck, playstyle, and turn structure.

They also start out with 20 health and 5 cards in their hand.
When a player's health is reduced to 0 (or below), the other player wins.

## Phases

Each player will start in their initial phase.

They may advance their phase forwards at any time.
Trying to advance from the final phase, will result in looping back to the initial phase.

Phases will follow the general structure of

1. Setup
2. Payoff
3. Retreat

## Turns

Within a turn, the following actions may be taken, in this order:

1. Advance your phase.
2. `Draw` 1. (Up to 5)
3. Play, activate, and maneuver cards whose requirements are met.
4. `Discard` 1, then `draw` 1.

## Cards

There are different card types:

- Creatures
- Structures
- Spells

During the player's second phase, their deployed cards may be activated
as long as they are not exhausted.

When a card it activated, it damages an orthogonally neighbouring card of choice for their `damage`.
This exhausts the card.

### Creatures

Creatures are deployed defensively on a lane,
and only if no other card is in that position.

If not exhausted, creatures may maneuver.
This exhausts them.

### Structures

Structures are deployed in the structure part of the lane,
and only if no other card is in that position.

### Spells

Spells may be deployed at any position, regardless of occupancy.
Spells will be activated immediately after being deployed.

## Card Piles

Each player's deck has two copies of each card in their character's `PlayerName.md` file.

There are three card piles:

- Draw pile
- Discard pile
- Graveyard

At the start of the game, the entire deck is shuffled, and placed onto the draw pile.

When a card is discarded, it moves to the discard pile.

When a deployed card's health drops to 0 or it is a deployed spell, it is moved to the graveyard.

When a player's draw and discard pile is empty, they can no longer draw cards.

When both player's draw piles are empty,
they may mutually decide to shuffle their discard piles into their draw piles.
The decision must be made right after the last card is drawn.
Once another action has been taken, this decision becomes binding.

Note that cards in the graveyard, stay in the graveyard, during this process.

## Health

All cards with a health value will start out with that amount of health.
This will be signaled by an amount of health cubes on the card.

There are red health cubes (worth 1),
and green ones, with a value of 5.

Damaging a card will remove an amount of health cubes from it,
while healing adds them.

If a card's health drops to 0, it dies and is placed in the graveyard.
This happens immediately, before any player actions.

A card may be healed until above its maximum health.

## Board

The board is made up of 4 pairs of lanes.
Each lane pair has 2×3 = 6 locations:

1. Structure
2. Defence
3. Offence

This makes the board look like:

| Lane / position | 0           | 1         | 2         | 3         | 4         | 5           |
| --------------- | ----------- | --------- | --------- | --------- | --------- | ----------- |
| A1 + A2         | Structure 1 | Defence 1 | Offence 1 | Offence 2 | Defence 2 | Structure 2 |
| B1 + B2         | Structure 1 | Defence 1 | Offence 1 | Offence 2 | Defence 2 | Structure 2 |
| C1 + C2         | Structure 1 | Defence 1 | Offence 1 | Offence 2 | Defence 2 | Structure 2 |
| D1 + D2         | Structure 1 | Defence 1 | Offence 1 | Offence 2 | Defence 2 | Structure 2 |

By default, a card can only attack cards orthogonally adjacent. (Encoded in its `Range`)

A creature in the opponent's defending position,
in a lane where the opponent does not have a structure,
may choose to attack their opponent directly.
