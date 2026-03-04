# Database Lab — Constraints and ALTER Operations

## Overview

This project demonstrates basic SQL database tasks including:

- Creating a database and tables with constraints
- Inserting records
- Testing constraint violations
- Applying ALTER operations
- Renaming tables

**Course:** CSE210 – Database Lab 
**Section:** 242D3  
**Lab:** Lab Report 01 – Constraints & ALTER

---

## Database: `library_lab`

---

## Tables and Constraints

### MEMBER

| Column    | Type | Constraints |
|-----------|------|-------------|
| MemberID  | INT  | PRIMARY KEY |
| FullName  | VARCHAR(100) | NOT NULL |
| Email     | VARCHAR(100) | NOT NULL, UNIQUE |
| Age       | INT  | CHECK (Age >= 12) |
| Gender    | ENUM('MALE','FEMALE','OTHER') | Optional |
| Phone     | VARCHAR(15) | NOT NULL DEFAULT 'N/A', CHECK(Phone <> '') |

---

### BOOK

| Column    | Type | Constraints |
|-----------|------|-------------|
| BookID    | INT  | PRIMARY KEY |
| Title     | VARCHAR(150) | NOT NULL |
| ISBN      | VARCHAR(20) | NOT NULL, UNIQUE |
| Price     | DECIMAL(8,2) | CHECK (Price >= 0) |
| Availability | ENUM('AVAILABLE','BORROWED') | DEFAULT 'AVAILABLE' |

---

### BORROW (Renamed from LOAN)

| Column    | Type | Constraints |
|-----------|------|-------------|
| LoanID    | INT  | PRIMARY KEY |
| MemberID  | INT  | FOREIGN KEY → MEMBER(MemberID) |
| BookID    | INT  | FOREIGN KEY → BOOK(BookID) |

---

## SQL Implementation

All SQL queries are available in this repository in the file:

