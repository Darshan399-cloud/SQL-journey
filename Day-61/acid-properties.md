# ACID Properties in SQL

ACID is a set of four important properties that ensure
database transactions are reliable.

## 1. Atomicity

Atomicity means a transaction is completed fully or not
completed at all.

Example:
- Money is deducted from Account A.
- Money is added to Account B.
- If the second operation fails, the first operation is
  rolled back.

## 2. Consistency

Consistency means a transaction keeps the database in
a valid state.

Example:
- Product stock should not become negative.
- Primary key and foreign key rules must remain valid.
- Database constraints must be maintained.

## 3. Isolation

Isolation means multiple transactions should not interfere
with each other incorrectly.

Example:
- Two users try to purchase the same product.
- The database manages concurrent operations to protect
  data accuracy.

## 4. Durability

Durability means committed changes remain saved even after
a system failure or restart.

Example:
- Once an order transaction is committed, its saved data
  remains stored in the database.

## ACID Summary

| Property | Meaning |
|----------|---------|
| Atomicity | All operations succeed or none |
| Consistency | Database remains valid |
| Isolation | Transactions do not interfere incorrectly |
| Durability | Committed data remains saved |

## Importance of ACID

1. Maintains data accuracy.
2. Prevents incomplete transactions.
3. Protects database consistency.
4. Supports concurrent users.
5. Improves transaction reliability.
6. Helps prevent incorrect financial records.
7. Ensures committed data is preserved.