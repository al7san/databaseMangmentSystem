# Definitions from the Reference (Database System Concepts, 7th Edition)

## **1. Transaction**
- **Definition:** A sequence of operations performed as a single logical unit of work. A transaction ensures ACID properties to maintain database integrity.
---
## **2. ACID Properties**
- **Atomicity:** Ensures that all operations in a transaction are completed; if any part fails, the transaction is aborted.
- **Consistency:** Ensures that a transaction transforms the database from one valid state to another.
- **Isolation:** Ensures that transactions do not interfere with each other.
- **Durability:** Ensures that the effects of a committed transaction are permanent, even in case of a system failure.

---

## **3. Recovery Schema**
- A recovery schema outlines the methods and mechanisms for restoring a database to a consistent state after a failure. This includes transaction logs, checkpoints, and rollback/redo operations.

---

## **4. LOMA (Lock-Ordered Multi-Version Architecture)**
- A concurrency control mechanism ensuring that locks on objects follow a strict order to prevent deadlocks while supporting multi-versioning for isolation.

---

## **5. NOMA (Non-Ordered Multi-Version Architecture)**
- A concurrency control mechanism that allows operations to access any version of the data without strict locking order, improving concurrency.

---

## **6. NUMA (Non-Uniform Memory Access)**
- **Definition:** A computer memory architecture where memory access time depends on the memory's proximity to the processor.
- **Use Case:** Improves performance in **shared-memory architectures** by reducing memory access bottlenecks.
- **Example System:** Multi-core processors in high-performance computing environments.

---

## **7. Schedule**
- A sequence of operations from multiple transactions that specifies the order in which the operations are executed. Schedules are evaluated for serializability to ensure correctness.

---

## **8. Shared-Memory Architecture**
- **Definition:** An architecture where processors share the same memory and storage. Communication between processors is fast due to shared memory.
- **Advantages:** High-speed communication.
- **Disadvantages:** Limited scalability due to contention for shared resources.

---

## **9. Data Servers**
- **Definition:** Servers that store and manage data items, allowing clients to fetch and process data locally. Common in client-server architectures.
- **Example:** JSON, XML-based servers used for semi-structured data.

---

## **10. Transaction Servers**
- **Definition:** Servers designed to handle transactions. They process queries, execute transactions, and manage data consistency and concurrency.
- **Example:** SQL servers like Oracle or Microsoft SQL Server.

---

## **11. Blockchain**
- **Definition:** A decentralized, distributed ledger that records transactions in linked blocks secured by cryptography.
- **Properties:** Decentralization, tamper resistance, anonymity, irrefutability.
- **Applications:** Cryptocurrencies, supply chain, health care, and IoT.

---

## **12. Full Node (Blockchain)**
- **Definition:** A node that maintains a complete copy of the blockchain and participates in the consensus process.

---

## **13. Light Node (Blockchain)**
- **Definition:** A node that interacts with the blockchain by submitting transactions but does not maintain the full blockchain or participate in the consensus process.

---

## **14. Parallel System**
- **Definition:** A database system that uses multiple processors and disks to process data in parallel for improved throughput and response time.

---
## **15. Concurrency Control**
- **Definition:** Mechanisms that ensure transactions are executed concurrently without violating the consistency of the database.
- **Examples:** Locking protocols, timestamp ordering, and optimistic concurrency control.

---
## **16. RDMA (Remote Direct Memory Access)**

**Remote Direct Memory Access (RDMA)** is a high-performance communication protocol that allows one computer to directly access the memory of another computer without involving the operating system or the CPU on either side. It significantly reduces latency and increases throughput in data transfers by bypassing traditional network protocol stacks.

---
# Quiz: Database Concepts

---

## Question 1:
What does the "A" in ACID properties stand for?  
- a) Accuracy  
- b) Atomicity  
- c) Accessibility  
- d) Adaptability  

<details>
<summary>Show Answer</summary>
**Answer:** b) Atomicity
</details>

---

## Question 2:
Which concurrency control mechanism ensures a strict order of locking to prevent deadlocks?  
- a) NOMA  
- b) LOMA  
- c) NUMA  
- d) Two-Phase Locking  

<details>
<summary>Show Answer</summary>
**Answer:** b) LOMA
</details>

---

## Question 3:
In which architecture do memory access times depend on proximity to the processor?  
- a) Shared-Disk  
- b) Shared-Nothing  
- c) NUMA  
- d) LOMA  

<details>
<summary>Show Answer</summary>
**Answer:** c) NUMA
</details>

---

## Question 4:
What is the main advantage of Shared-Nothing architecture?  
- a) Low communication costs  
- b) High scalability  
- c) Fast access to shared memory  
- d) Fault tolerance  

<details>
<summary>Show Answer</summary>
**Answer:** b) High scalability
</details>

---

## Question 5:
Which node in a blockchain maintains a complete copy and participates in the consensus process?  
- a) Light Node  
- b) Full Node  
- c) Data Server  
- d) Validator  

<details>
<summary>Show Answer</summary>
**Answer:** b) Full Node
</details>

---

## Question 6:
Which blockchain property ensures users cannot deny submitting a transaction?  
- a) Tamper resistance  
- b) Anonymity  
- c) Irrefutability  
- d) Decentralization  

<details>
<summary>Show Answer</summary>
**Answer:** c) Irrefutability
</details>

---

## Question 7:
Transactions are required to satisfy ACID properties to maintain database integrity.  
- **True**  
- **False**  

<details>
<summary>Show Answer</summary>
**Answer:** True
</details>

---

## Question 8:
NOMA guarantees strict locking order to prevent deadlocks.  
- **True**  
- **False**  

<details>
<summary>Show Answer</summary>
**Answer:** False (This describes LOMA)
</details>

---

## Question 9:
Shared-Memory architecture scales well to thousands of processors.  
- **True**  
- **False**  

<details>
<summary>Show Answer</summary>
**Answer:** False (Scalability is limited due to memory contention.)
</details>

---

## Question 10:
Parallel systems aim to improve throughput and response time by using multiple processors and disks.  
- **True**  
- **False**  

<details>
<summary>Show Answer</summary>
**Answer:** True
</details>

---

## Question 11:
In the Tree Protocol, once a node is unlocked, it can be locked again during the same transaction.  
- **True**  
- **False**  

<details>
<summary>Show Answer</summary>
**Answer:** False (Once a node is unlocked, it cannot be locked again.)
</details>

---

## Question 12:
A light node in a blockchain participates in the consensus process.  
- **True**  
- **False**  

<details>
<summary>Show Answer</summary>
**Answer:** False (Light nodes do not participate in the consensus process.)
</details>

---

## Question 13:
Recovery schema ensures a database returns to a consistent state after a failure.  
- **True**  
- **False**  

<details>
<summary>Show Answer</summary>
**Answer:** True
</details>

---

## Question 14:
LOMA allows locking without a strict hierarchical order.  
- **True**  
- **False**  

<details>
<summary>Show Answer</summary>
**Answer:** False (LOMA enforces a strict order for locking.)
</details>

---

## Question 15:
Blockchain applications include supply chain management, health care, and cryptocurrencies.  
- **True**  
- **False**  

<details>
<summary>Show Answer</summary>
**Answer:** True
</details>

---

## Question 16:
Which of the following is a blockchain consensus mechanism?  
- a) Proof of Activity  
- b) Proof of Stake  
- c) Proof of Capacity  
- d) All of the above  

<details>
<summary>Show Answer</summary>
**Answer:** d) All of the above
</details>

---

## Question 17:
What is the term for a blockchain’s first block?  
- a) Genesis Block  
- b) Root Block  
- c) Parent Block  
- d) Primary Block  

<details>
<summary>Show Answer</summary>
**Answer:** a) Genesis Block
</details>

---

## Question 18:
In NUMA architecture, memory access times are:  
- a) Uniform for all processors  
- b) Variable depending on proximity  
- c) Faster than shared-nothing architecture  
- d) Determined by lock managers  

<details>
<summary>Show Answer</summary>
**Answer:** b) Variable depending on proximity
</details>

---

## Question 19:
Which of the following is a use case for parallel systems?  
- a) High-performance transaction processing  
- b) Scientific simulations  
- c) Decision support queries  
- d) All of the above  

<details>
<summary>Show Answer</summary>
**Answer:** d) All of the above
</details>

---

## Question 20:
Which of the following is NOT an ACID property?  
- a) Isolation  
- b) Decentralization  
- c) Durability  
- d) Consistency  

<details>
<summary>Show Answer</summary>
**Answer:** b) Decentralization
</details>

---

## Question 21:
What is the primary goal of concurrency control?  
- a) Maximize parallelism  
- b) Prevent data loss  
- c) Maintain database consistency  
- d) Reduce memory usage  

<details>
<summary>Show Answer</summary>
**Answer:** c) Maintain database consistency
</details>

---

## Question 22:
In a transaction server, queries are processed:  
- a) By a decentralized blockchain  
- b) Centrally within the server  
- c) In the client's local memory  
- d) Using a shared-nothing architecture  

<details>
<summary>Show Answer</summary>
**Answer:** b) Centrally within the server
</details>

---

## Question 23:
Which property of blockchain ensures tamper resistance?  
- a) Cryptographic hashes  
- b) Light nodes  
- c) Proof of Activity  
- d) Decentralization  

<details>
<summary>Show Answer</summary>
**Answer:** a) Cryptographic hashes
</details>

---

## Question 24:
Shared-Disk architectures are fault-tolerant because all processors share:  
- a) The same memory  
- b) Private storage  
- c) Disk access  
- d) Interconnection networks  

<details>
<summary>Show Answer</summary>
**Answer:** c) Disk access
</details>

---

## Question 25:
Which type of node in a blockchain only submits transactions but does not store the full blockchain?  
- a) Full Node  
- b) Validator Node  
- c) Light Node  
- d) Miner  

<details>
<summary>Show Answer</summary>
**Answer:** c) Light Node
</details>

---

## Question 26:
NUMA architectures are commonly used in:  
- a) Shared-memory systems  
- b) Blockchain networks  
- c) Two-phase locking protocols  
- d) Shared-disk systems  

<details>
<summary>Show Answer</summary>
**Answer:** a) Shared-memory systems
</details>

---

## Question 27:
In Two-Phase Locking (2PL), a transaction can acquire locks in the shrinking phase.  
- **True**  
- **False**  

<details>
<summary>Show Answer</summary>
**Answer:** False
</details>

---

## Question 28:
Cryptographic hashes ensure anonymity in blockchain systems.  
- **True**  
- **False**  

<details>
<summary>Show Answer</summary>
**Answer:** False (Cryptographic hashes ensure tamper resistance, not anonymity.)
</details>

---

## Question 29:
Parallel systems enhance database performance by executing queries sequentially.  
- **True**  
- **False**  

<details>
<summary>Show Answer</summary>
**Answer:** False (Parallel systems execute queries concurrently.)
</details>

---

## Question 30:
The recovery schema helps restore a database to a consistent state after a failure.  
- **True**  
- **False**  

<details>
<summary>Show Answer</summary>
**Answer:** True
</details>

---

## Question 31:
Light nodes in a blockchain perform consensus and store the entire chain.  
- **True**  
- **False**  

<details>
<summary>Show Answer</summary>
**Answer:** False (Light nodes do not perform consensus or store the full chain.)
</details>

---

## Question 32:
Two-Phase Locking (2PL) ensures deadlock prevention.  
- **True**  
- **False**  

<details>
<summary>Show Answer</summary>
**Answer:** False (2PL does not prevent deadlocks.)
</details>

---
## 33. What does RDMA allow computers to do?
- a) Share operating systems  
- b) Directly access each other's memory  
- c) Use each other's CPUs  
- d) Transfer data using traditional protocols  

<details>
<summary>Show Answer</summary>
**Answer:** b) Directly access each other's memory
</details>

---
## 34. Which of the following is NOT a characteristic of RDMA?
- a) Low latency  
- b) High CPU utilization  
- c) High throughput  
- d) Bypassing traditional network protocols  

<details>
<summary>Show Answer</summary>
**Answer:** b) High CPU utilization
</details>

---

## 35. What component handles data transfers in RDMA?
- a) Operating System  
- b) CPU  
- c) Network Interface Card (NIC)  
- d) Application Layer  

<details>
<summary>Show Answer</summary>
**Answer:** c) Network Interface Card (NIC)
</details>

---
## 36. RDMA reduces data transfer latency by bypassing traditional network protocol stacks.
- **True**  
- **False**

<details>
<summary>Show Answer</summary>
**Answer:** True
</details>

---

## 37. RDMA requires constant involvement of the operating system during data transfers.
- **True**  
- **False**

<details>
<summary>Show Answer</summary>
**Answer:** False (RDMA bypasses the operating system during transfers.)
</details>

---

## 38. RDMA allows one computer to access another computer's memory without CPU involvement.
- **True**  
- **False**

<details>
<summary>Show Answer</summary>
**Answer:** True
</details>

---

## 39. RDMA increases CPU usage during memory access.
- **True**  
- **False**

<details>
<summary>Show Answer</summary>
**Answer:** False (RDMA reduces CPU usage by offloading data transfer to the NIC.)
</details>

---
## 40. RDMA is commonly used in distributed databases and high-performance computing.
- **True**  
- **False**

<details>
<summary>Show Answer</summary>
**Answer:** True
</details>
