# Lazy-Update-AVL-Tree

A C++ container implementing an AVL Tree with Lazy Propagation support for efficient interval updates and queries. It combines the self-balancing properties of AVL trees with the deferred update logic.

## Academic Context

This project was developed as a part of a university assignment at **FIT CTU** (Czech Technical University in Prague).

* The core logic, including the **AVL rebalancing**, **tree rotations**, and **lazy update propagation**, is my original implementation.
* The testing framework (including the `Ref` class, `Tester` struct, and `main` function) was provided as part of the course materials to verify correctness.

## Features

* **AVL Balancing:** Automatically maintains tree height balance using rotations (LL, RR, LR, RL) to ensure $O(\log n)$ complexity for basic operations.
* **Lazy Propagation:** Efficiently handles range updates (e.g., "add 5 to all keys between 10 and 20") by deferring operations until nodes are accessed.
* **Generic Design:** Fully templated implementation allowing custom types for Keys, Values, and aggregation Operations.
* **Range Operations:** optimized `update` method capable of modifying values across a span of keys without visiting every single node.

## Technical Details

The implementation relies on several key algorithms:
* **Push-Down Mechanism:** Before any node is processed or rotated, pending updates are propagated to its children (`pushDownUpdate`), ensuring data consistency.
* **LCA Traversal:** The range update logic identifies the Least Common Ancestor of the interval boundaries to minimize tree traversal.
* **Tree Rotations:** Standard AVL rotations are augmented to handle lazy tags, ensuring that structural changes do not lose pending update information.
* **Parent Pointers:** Nodes maintain pointers to their parents to facilitate bottom-up rebalancing after insertions and deletions.

## Disclaimer

If you are a student currently enrolled in the same course, please be aware of your university's academic integrity policy. This code is shared for portfolio purposes only.
