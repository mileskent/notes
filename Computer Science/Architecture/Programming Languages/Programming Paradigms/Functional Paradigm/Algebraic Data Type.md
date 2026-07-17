---
date: 2026-07-12
aliases:
  - ADT
---
A composite [[Data Type]] formed by combining other types using two fundamental operations. Called "algebraic" because types form a [[Semiring]] under sum (+) and product (\*), with the void/never type as additive identity (0) and the unit type as multiplicative identity (1).

# Algebraic Data Type Semiring Forms
## Sum Type
Tagged unions, variants, coproducts. An "OR" type.
* e.g. the "Traffic light signal" type is Red **or** Yellow **or** Green.
## Product Type
Records, tuples, structs. An "AND" type.
* e.g. the "3D [[Coordinate Vector]]" type is an X **and** a Y **and** a Z coordinate.
## Void Type
Represents the lack of a value. A [[#Sum Type]] with no variants.
## Unit Type
Represents a type with exactly one value. It is a [[#Sum Type]] with one variant.

# Examples
## Deck of Cards
* Types
	* "Suit" is a "Hearts" **or** a "Diamonds" **or** a "Clubs" **or** a "Spades"
	* "Rank" is an "Ace" **or** a "2" **or** ... **or** a "King"
	* "Card" is a "Suit" **and** a "Rank"
* Ace of Spades = Card(Spades, Ace)