## 1- Consider a database for an airline where the database system uses snapshot isolation.Describe a particular scenario in which a nonserializable execution occurs,but the airline may be willing to accept it in order to gain better overall performance.
### Answer:
Consider a web-based airline reservation system. There could be many concurrent requests to see the list of available flights and available seats in each flight and to book tickets. 
Suppose there are two users, **A** and **B**, concurrently accessing this web application, and only one seat is left on a flight.

Suppose that both user **A** and user **B** execute transactions to book a seat on the flight and suppose that each transaction checks the total number of seats booked on the 
flight and inserts a new booking record if there are enough seats left. Let `T₃` and `T₄` be their respective booking transactions, which run concurrently. Now `T₃` and `T₄` will see 
from their snapshots that one ticket is available and will insert new booking records. Since the two transactions do not update any common data item (tuple), snapshot isolation allows both transactions to commit. 
This results in an extra booking, beyond the number of seats available on the flight.

However, this situation is usually not very serious since cancellations often resolve the conflict; even if the conflict is present at the time the flight is to leave,
the airline can arrange a different flight for one of the passengers on the flight, giving incentives to accept the change. Using snapshot isolation improves the overall 
performance in this case since the booking transactions read the data from their snapshots only and do not block other concurrent transactions.

---
## 2- Consider the following two transactions:

### T₃₄:
- `read(A);`
- `read(B);`
- `if A = 0 then B := B + 1;`
- `write(B).`

### T₃₅:
- `read(B);`
- `read(A);`
- `if B = 0 then A := A + 1;`
- `write(A).`

**Question:**  
Add lock and unlock instructions to transactions T₃₁ and T₃₂ so that they observe the two-phase locking protocol. Can the execution of these transactions result in a deadlock?

### Answer:

#### a. Lock and unlock instructions:

**T₃₄:**
- `lock-S(A)`
- `read(A)`
- `lock-X(B)`
- `read(B)`
- `if A = 0`
  - `then B := B + 1`
- `write(B)`
- `unlock(A)`
- `unlock(B)`

**T₃₅:**
- `lock-S(B)`
- `read(B)`
- `lock-X(A)`
- `read(A)`
- `if B = 0`
  - `then A := A + 1`
- `write(A)`
- `unlock(B)`
- `unlock(A)`

#### b. Execution of these transactions can result in deadlock. For example, consider the following partial schedule:

| **T₃₁**          | **T₃₂**          |
|-------------------|------------------|
| `lock-S(A)`       |                  |
|                   |  `lock-S(B)`     |
|                   |  `read(B)`       |
| `read(A)`         |                  |
| `lock-X(B)`       |                  |
|                   | `lock-X(A)`      |

**The transactions are now deadlocked.**
---
###3- Question:
Show by example that there are schedules possible under the tree protocol that are not possible under the two-phase locking protocol, and vice versa.

### Answer:
Consider the tree-structured database graph given below.

 A
 |
 B
 |
 C
### Tree Protocol vs Two-Phase Locking Protocol


#### Example 1: Schedule possible under tree protocol but not under 2PL:

### Tree Protocol vs Two-Phase Locking Protocol

#### Example 1: Schedule possible under tree protocol but not under 2PL:

| **T₁**          | **T₂**          |
|------------------|-----------------|
| `lock(A)`       |                 |
| `lock(B)`       |                 |
| `unlock(A)`     |                 |
### Tree Protocol vs Two-Phase Locking Protocol

#### Example 1: Schedule possible under tree protocol but not under 2PL:

| **T₁**          | **T₂**          |
|------------------|-----------------|
| `lock(A)`       |                 |
| `lock(B)`       |                 |
| `unlock(A)`     |                 |
|                 | `lock(A)`       |
| `lock(C)`       |                 |
| `unlock(B)`     |                 |
|                 | `lock(B)`       |
|                 | `unlock(A)`     |
|                 | `unlock(B)`     |
|  `unlock(C)`    |                 |

---

#### Example 2: Schedule possible under 2PL but not under tree protocol:

| **T₁**          | **T₂**          |
|------------------|-----------------|
| `lock(A)`       | `lock(B)`       |
| `lock(C)`       | `unlock(B)`     |
| `unlock(A)`     |                 |
| `unlock(C)`     |                 |

| `unlock(B)`     | `lock(B)`       |
| `unlock(C)`     | `unlock(A)`     |
|                 | `unlock(B)`     |

---

#### Example 2: Schedule possible under 2PL but not under tree protocol:

| **T₁**          | **T₂**          |
|------------------|-----------------|
| `lock(A)`       | `lock(B)`       |
| `lock(C)`       | `unlock(B)`     |
| `unlock(A)`     |                 |
| `unlock(C)`     |                 |


