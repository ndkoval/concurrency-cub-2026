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

