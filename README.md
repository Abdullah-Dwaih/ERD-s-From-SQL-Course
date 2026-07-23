# ERD's From SQL Course

A collection of Entity-Relationship Diagrams (ERDs) designed and practiced as part of the **SQL Course** on [Programming Advices](https://programmingadvices.com) by **Dr. Mohammed Abu Hudhud**.

Each diagram was built using **draw.io**, following the SQL Server data-typing conventions taught in the course, and represents a real-world business domain modeled from scratch: identifying entities, defining attributes, choosing primary/foreign keys, and resolving relationships (1:1, 1:M, M:N).

---

## 📂 Projects

| # | Project | Domain | File |
|---|---------|--------|------|
| 1 | [Simple Online Shop](ERDs/SimpleOnlineShop.drawio.svg) | E-commerce | `SimpleOnlineShop_drawio.svg` |
| 2 | [Car Rental System](ERDs/CarRentalERD.drawio.svg) | Vehicle Rental | `CarRentalERD_drawio.svg` |
| 3 | [Simple Clinic](ERDs/SimpleClinicERD.svg) | Healthcare | `SimpleClinicERD.svg` |
| 4 | [Simple Library](ERDs/SimpleLibraryERD.drawio.svg) | Library Management | `SimpleLibraryERD_drawio.svg` |
| 5 | [Karate Club](ERDs/KarateClub.drawio.svg) | Membership & Training | `KarateClub_drawio.svg` |

---

## 1. 🛒 Simple Online Shop

An ERD for an e-commerce platform covering the full order lifecycle — from browsing a product catalog to checkout, payment, shipping, and post-purchase reviews.

**Core Entities:** `Customers`, `ProductsCatalog`, `ProductsCategories`, `ProductImages`, `Orders`, `OrderItems`, `Payments`, `Shipping`, `Reviews`

**Key Concepts Demonstrated:**
- Composite Primary Key on `OrderItems (OrderID, ProductID)` to resolve the Many-to-Many relationship between Orders and Products
- One-to-Many relationships: one Customer → many Orders, one Order → many OrderItems
- Separating `ProductImages` into its own table to support multiple images per product

---

## 2. 🚗 Car Rental System

Models the operations of a vehicle rental business: customer bookings, active rentals, returns, and vehicle maintenance history.

**Core Entities:** `Customers`, `VehicleInfo`, `VehicleBooking`, `RentalTransaction`, `VehicleReturns`, `Maintenance`, `FuleType`, `VehicleCategory`

**Key Concepts Demonstrated:**
- Splitting the rental process into distinct stages (`Booking` → `Transaction` → `Return`) instead of one large table
- Lookup tables (`FuleType`, `VehicleCategory`) to normalize repeated vehicle attributes
- Tracking vehicle maintenance independently from rental activity

---

## 3. 🏥 Simple Clinic

A healthcare-domain ERD managing patients, doctors, appointments, prescriptions, and billing.

**Core Entities:** `Person`, `Patient`, `Doctor`, `AppointMent`, `MedicalRecord`, `Prescription`, `Payments`

**Key Concepts Demonstrated:**
- **Table inheritance pattern:** `Patient` and `Doctor` both reference a shared `Person` table (avoiding duplicate name/contact fields)
- Linking `MedicalRecord` to both `Doctor` and `Patient` to preserve the full visit context
- Separating `Prescription` from `MedicalRecord` since one visit can result in multiple prescribed medications

---

## 4. 📚 Simple Library

Models a library's book inventory, borrowing process, and fine system.

**Core Entities:** `Books`, `Copes` (Copies), `Users`, `BorrowingRecords`, `Fine`, `Reservation`, `Settings`

**Key Concepts Demonstrated:**
- Distinguishing between a `Book` (the title/metadata) and a `Cope` (a physical copy) — since a library owns multiple copies of the same book
- `BorrowingRecords` as a transactional table linking Users to specific Copies with due/return dates
- A `Settings` table for global, non-relational configuration (default borrowing period, fine-per-day)

---

## 5. 🥋 Karate Club

A membership-management ERD for a martial arts club: members, instructors, belt progression, and payments.

**Core Entities:** `Persons`, `Members`, `Instructors`, `BeltsRank`, `BeltsTests`, `InstructorsMembers`, `SubscriptionPeriod`, `Payments`

**Key Concepts Demonstrated:**
- Shared `Persons` table as the base entity for both `Members` and `Instructors`
- Composite Primary Key on `InstructorsMembers (InstructorID, MemberID)` to model which instructor trains which member
- Tracking belt progression over time through `BeltsTests` linked to `BeltsRank`

---

## 🛠️ Tools & Concepts Covered

- **Design Tool:** draw.io
- **Target DBMS:** SQL Server (T-SQL data types: `nvarchar`, `smallmoney`, `datetime`, `bit`, etc.)
- **Concepts practiced across projects:**
  - Primary Keys (Simple & Composite)
  - Foreign Keys & Referential relationships
  - Resolving Many-to-Many relationships via junction tables
  - Table inheritance / shared base entities
  - Normalization principles (1NF–3NF)

---

## 👤 About Me

Computer Engineering Technology student, currently working through the SQL learning path on **Programming Advices**. This repository documents hands-on ERD design practice as part of that journey.

**Course:** SQL — Programming Advices (Dr. Mohammed Abu Hudhud)
**Current Progress:** Course 17 — Projects & Practice

---

⭐ Feel free to explore the diagrams, and connect with me if you'd like to discuss database design!
