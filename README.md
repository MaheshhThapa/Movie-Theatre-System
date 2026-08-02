# Movie Theatre Management System — Use Case Diagram

## Overview
This repository contains the Use Case Diagram (UCD) for an online movie theatre
booking system that replaces a manual, in-person ticket booking process.

## Actors
| Actor | Description |
|---|---|
| **Customer** | Browses movies/shows and reserves seats. |
| **Theatre Staff** | Manages movies, show schedules, and reservations. |
| **Payment Gateway** *(external system)* | Processes payment during booking. |

## Use Cases

**Core booking flow**
- Browse Movies & Show Schedules
- Reserve Seats
- Confirm Reservation
- Provide Customer Details *(`<<include>>` of Confirm Reservation)*
- Make Payment *(`<<include>>` of Confirm Reservation)*

**Optional add-ons**
- Select Snacks *(`<<extend>>` of Reserve Seats)*
- Select Premium Seating *(`<<extend>>` of Reserve Seats)*

**Staff administration**
- Manage Movies
- Manage Show Schedules
- Manage Reservations

## Design Notes
- A reservation cannot be confirmed until the customer's details are captured
  **and** payment is completed — modeled as mandatory `<<include>>`
  relationships from *Confirm Reservation*.
- Snacks and premium seating are optional, customer-driven additions —
  modeled as `<<extend>>` relationships on *Reserve Seats*.
- The booking process is identical across all screening categories (e.g. 2D,
  3D, Premium). Category is treated as a data attribute of a show rather than
  a separate use case, so no actor/use-case generalization was needed for
  this.

## Files
- `Movie-Theatre-System.pdf` — the use case diagram.
