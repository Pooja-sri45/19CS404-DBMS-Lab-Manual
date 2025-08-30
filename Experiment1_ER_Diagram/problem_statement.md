# ER Diagram Workshop – Submission Template
## NAME:POOJASRI L
## REG.NO:212223220076
## DATE:30/08/2025

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
![WhatsApp Image 2025-08-29 at 18 20 22_383635d5](https://github.com/user-attachments/assets/b7f4f3bc-9dd5-486d-8de8-7015816f1f7c)


### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
| Member       |  MemberID (PK), Name, Age, MembershipType, StartDate                  |   Stores details of gym members    |
| Program       |  ProgramID (PK), ProgramName, Type                  |Represents fitness programs (Yoga, Zumba, etc.)       |
| Trainer       |  TrainerID (PK), Name, Expertise                  |  Trainers who conduct/lead programs     |
| Session       |   SessionID (PK), Date, TrainerID (FK)                 | Individual sessions (group/personal training)      |
| Payment       |  PaymentID (PK), Account, Amount, Date                  |  Records payments for memberships or sessions     |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
| Member – Program             |   M:N         | Optional for Member, Mandatory for Program        | Member may or may not join programs      |
|  Trainer – Program       |   M:N          |  Mandatory for both             | Trainer may or may not run Programs      |
|  Member – Payment            |   1:N        |  Mandatory for Payment             |Payments belong to members |

### Assumptions
- Every member must enroll in at least one program.

- Each program must have at least one trainer assigned.

- Payments are always linked to members (no anonymous payments).
 

---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
![WhatsApp Image 2025-08-29 at 18 58 43_bd5ce43e](https://github.com/user-attachments/assets/ab20d657-0baf-4f2a-9316-45b942326daf)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
| Member       |  MemberID (PK), Name, Age                  |  Library members who borrow books and attend events     |
| Book       |  BookID (PK), Title, Author, Category                  | Books available for borrowing      |
| Event       |  EventID (PK), ProgramID, Date                  | Events organized by the library      |
|  Room      |    RoomID (PK), Name                | Rooms for study or events      |
|  Speaker      | SpeakerID (PK), Name                   | Speakers/authors who present at events      |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|  Member – Book            |  M:N          |   Mandatory for Book            | Members borrow books      |
|  Event – Room            |         M:N            | Mandatory for Event|      Events are held in rooms|
|   Event – Speaker          |   M:N            |Mandatory for Event  |   Events have speakers  |

### Assumptions
- Each book can be borrowed by one member at a time.

- Each event must have at least one speaker and one booked room.

- Overdue fines apply only when books are not returned on time.
  
---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
![WhatsApp Image 2025-08-29 at 18 33 25_93afd7c3](https://github.com/user-attachments/assets/a3915b1b-61ce-4058-aa5e-0a97797a7aca)



### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|  Customer      |CustomerID (PK), Name, Phone_No |  Customers reserving tables or ordering food     |
|  Waiter      |   WaiterID (PK), Name|  Waiters serve reservations/orders            |
| Reservation/Order       |  OrderID (PK), Date, Time, Guests | Customer reservations and placed orders                  |
| Dish       |   DishID (PK), Name, CategoryNo (FK)|Dishes available to order                     |
| Category       |  CategoryNo (PK), CategoryName| Dish classification (Starter, Main, Dessert)             |
|Bill | BillID (PK), Amount, Total|Bill generated for each order                     |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
| Customer – Waiter             |  1:1          |Mandatory               | Each reservation handled by one waiter      |
|  Order – Dishes            |   M:N         |   Mandatory for order            |     An order contains many dishes  |
|  Order – Bill            |    1:M        |   Mandatory for Bill            |  Each order generates one bill     |

### Assumptions
- Each reservation/order is served by one waiter.

- A dish belongs to exactly one category.

- Bills are generated only after placing an order.

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
