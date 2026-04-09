# Comic-Con Multi-Zone Parking System — ER Diagram

## Overview

This project contains the Entity Relationship Diagram (ERD) for a multi-zone event parking system designed for large conventions like Comic-Con. The system manages vehicle entry, parking spot allocation, ticket generation, parking sessions, reserved categories, and payment tracking.

The design supports multiple zones, levels, vehicle types, and reusable parking spots across different sessions.

---

## System Workflow

Vehicle → Ticket Generated → Parking Spot Assigned → Parking Session
→ Exit Time Recorded → Fee Calculated → Payment Completed

---

## Features Covered

* Vehicle entry tracking
* Vehicle type categories (Bike, Car, SUV, EV)
* Multi-zone parking facility
* Multiple parking levels
* Reserved parking categories (VIP, Staff, Exhibitors, EV)
* Parking spot allocation
* Entry and exit timestamps
* Parking session tracking
* Parking ticket generation
* Spot reuse across sessions
* Parking fee calculation
* Payment tracking
* Track currently parked vehicles
* Availability tracking

---

## Entities

### Vehicle Categories

Stores vehicle types.

* category_id (PK)
* category_name

---

### Vehicles

Stores vehicle details.

* vehicle_id (PK)
* vehicle_number
* category_id (FK)

---

### Parking Zones

Represents zone and level.

* zone_id (PK)
* zone_name
* level

---

### Spot Categories

Reserved parking types.

* spot_category_id (PK)
* category_name

Examples:

* VIP
* Staff
* Exhibitor
* EV Charging
* Cosplayer

---

### Parking Spots

Individual parking slots.

* spot_id (PK)
* zone_id (FK)
* spot_category_id (FK)
* spot_number
* is_available

---

### Tickets

Generated on vehicle entry.

* ticket_id (PK)
* ticket_number
* issued_at

---

### Parking Sessions

Tracks entry and exit.

* session_id (PK)
* vehicle_id (FK)
* spot_id (FK)
* ticket_id (FK)
* entry_time
* exit_time
* fee
* status

---

### Payments

Stores payment information.

* payment_id (PK)
* session_id (FK)
* amount
* payment_method
* payment_status
* paid_at

---

## Relationships

* One vehicle can have multiple parking sessions
* One parking spot can be reused across sessions
* One zone contains multiple parking spots
* One spot category assigned to many spots
* Each session generates one ticket
* Each session has one payment
* Vehicle category assigned to vehicles

---

## Business Rules

* One vehicle can enter multiple times
* One parking spot reused over time
* Sessions store entry and exit time
* Tickets generated per entry
* Reserved parking supported
* EV charging spots supported
* Multi-zone parking supported
* Payment linked to session
* Availability tracked using sessions

---

## ER Diagram

The ER diagram includes:

* Primary keys
* Foreign keys
* Normalized structure
* Multi-zone parking model
* Ticket and session separation
* Payment structure
* Reserved parking categories

---

## Files

```
parking-system-erd
│
├── README.md
├── parking-erd.txt
└── diagram.png
```

---

## Use Cases Supported

* Track all vehicles inside venue
* Assign parking based on vehicle type
* Handle VIP reserved parking
* Track EV charging spots
* Calculate parking fees
* Generate tickets
* Track exit times
* Record payments
* Reuse parking spots
* Multi-day event support

---

## Assignment

Web Dev Cohort 2026
Database Design - Multi-Zone Event Parking System
Comic-Con Venue Parking Management
