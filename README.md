# Intensive Course on Concurrent Programming

All tasks are tested automatically by GitHub Actions on every push
(see the *Actions* tab of your repository).

## Day 1: Locks and Stack

### Coarse-grained bank

In [`src/day1/CoarseGrainedBank.kt`](src/day1/CoarseGrainedBank.kt),
make the sequential bank implementation thread-safe.
Please follow the *coarse-grained locking* scheme to make synchronization efficient.
For that, you need to use a single lock to protect all bank operations.

To test your solution, please run:

* `./gradlew test --tests CoarseGrainedBankTest` on Linux or MacOS
* `gradlew test --tests CoarseGrainedBankTest` on Windows

### Fine-grained bank

In [`src/day1/FineGrainedBank.kt`](src/day1/FineGrainedBank.kt),
make the sequential bank implementation thread-safe.
Please follow the *fine-grained locking* scheme to make synchronization efficient.
For that, you need to use per-account locks, thus, ensuring natural parallelism
when accessing different accounts. The `totalAmount()` function should acquire
all the locks to get a consistent snapshot, while `transfer(..)` should acquire
the corresponding account locks.

To test your solution, please run:

* `./gradlew test --tests FineGrainedBankTest` on Linux or MacOS
* `gradlew test --tests FineGrainedBankTest` on Windows

### Treiber stack

In [`src/day1/TreiberStack.kt`](src/day1/TreiberStack.kt),
implement the classic Treiber stack algorithm.

To test your solution, please run:

* `./gradlew test --tests TreiberStackTest` on Linux or MacOS
* `gradlew test --tests TreiberStackTest` on Windows

### Treiber stack with elimination

In [`src/day1/TreiberStackWithElimination.kt`](src/day1/TreiberStackWithElimination.kt),
implement the classic Treiber stack algorithm with the elimination technique.

To test your solution, please run:

* `./gradlew test --tests TreiberStackWithEliminationTest` on Linux or MacOS
* `gradlew test --tests TreiberStackWithEliminationTest` on Windows

## Day 2: Michael-Scott Queue

### Michael-Scott queue

In [`src/day2/MSQueue.kt`](src/day2/MSQueue.kt),
implement the classic Michael-Scott queue algorithm.

To test your solution, please run:

* `./gradlew test --tests MSQueueTest` on Linux or MacOS
* `gradlew test --tests MSQueueTest` on Windows


## Day 3: FAA-Based Queue

### FAA-based queue

In [`src/day3/FaaBasedQueue.kt`](src/day3/FaaBasedQueue.kt),
implement a concurrent queue that leverages the `Fetch-and-Add` synchronization primitive.
The queue is built on an infinite array, which is simulated with a linked list of
fixed-size segments, maintained similarly to the Michael-Scott queue.

To test your solution, please run:

* `./gradlew test --tests FAABasedQueueTest` on Linux or MacOS
* `gradlew test --tests FAABasedQueueTest` on Windows

## Day 4: Removals from the Middle

### Michael-Scott queue with linear-time removals

In [`src/day4/MSQueueWithLinearTimeRemove.kt`](src/day4/MSQueueWithLinearTimeRemove.kt),
implement a Michael-Scott queue with an additional `remove(element)` operation.
The removal is split into two phases: first, the node is marked as logically removed;
then, it is physically unlinked by finding the previous node, which takes linear time.

To test your solution, please run:

* `./gradlew test --tests MSQueueWithLinearTimeRemoveTest` on Linux or MacOS
* `gradlew test --tests MSQueueWithLinearTimeRemoveTest` on Windows

### Michael-Scott queue with constant-time removals

In [`src/day4/MSQueueWithConstantTimeRemove.kt`](src/day4/MSQueueWithConstantTimeRemove.kt),
implement a Michael-Scott queue with an additional `remove(element)` operation.
Unlike in the previous task, each node maintains a `prev` pointer to the previous node,
so the physical removal works in constant time under no contention.

To test your solution, please run:

* `./gradlew test --tests MSQueueWithConstantTimeRemoveTest` on Linux or MacOS
* `gradlew test --tests MSQueueWithConstantTimeRemoveTest` on Windows

## Day 5: Multi-Word CAS

### CAS2

In [`src/day5/AtomicArrayWithCAS2.kt`](src/day5/AtomicArrayWithCAS2.kt),
implement the `cas2(..)` operation, which atomically updates two array cells
if both of them contain the expected values. Use descriptors to make the operation
linearizable and lock-free, helping other threads to complete their operations.

To test your solution, please run:

* `./gradlew test --tests AtomicArrayWithCAS2Test` on Linux or MacOS
* `gradlew test --tests AtomicArrayWithCAS2Test` on Windows
