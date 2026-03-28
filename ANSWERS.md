# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

- A `process` is an independent program in execution that has its own dedicated memory space and resources, while a `thread` is a smaller unit of execution that lives inside a process.
- `Threads` are often called "lightweight processes" because they share the same memory and resources of their parent process, which makes communication between them much faster.
- In the assignment, we used threads instead of processes because creating a thread has much lower overhead and uses less system memory.
- This was more suitable for our simulation because we needed many processes to run at the same time and share the same `processMap` and `readyQueue` to track their progress efficiently.

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

- In Round-Robin scheduling, if a process does not finish its work during the given time quantum, the CPU interrupts it and performs a context switch.
- The process is then moved from `Running` state back to the end of the `Ready Queue` so other processes can use the CPU.
- In the program, i achieved this by checking if `(!process.isFinished())` and then calling `processQueue.add(thread)` to re-enqueue it.

Example from my output:
```
┌─ Ready Queue ─────────────────────────────────────────────────────────────────
│ [P9 ? P4 ? P3 ? P10 ? P5 ? P6 ? P7 ? P1 ? P8]
└───────────────────────────────────────────────────────────────────────────────

  ? P2 executing quantum [4000ms]
  ? Quantum progress: [███████████████] 100%
  ? P2 completed quantum 4000ms │ Overall progress: [███████████████░░░░░] 76%
     Remaining time: 1218ms
  ? P2 yields CPU for context switch

  ? P2 added to ready queue (Priority: 5)  │ Burst time: 5218ms
┌─ Ready Queue ─────────────────────────────────────────────────────────────────
│ [P2 ? P4 ? P3 ? P10 ? P5 ? P6 ? P7 ? P1 ? P8]
└───────────────────────────────────────────────────────────────────────────────
```

**Explanation of example:**
- In this snippet, The process P2 started executing with a burst time of 5218ms, but the time quantum was set to 4000ms.
-  Because P2 could not finish its work within the allowed time, a context switch occurred, and the system displayed "P2 yields CPU."

- Also since we are using a PriorityQueue, P2 was not just sent to the back of the line. Because P2 has a high priority of 5, it was re-inserted at the front of the queue (as shown in the second Ready Queue).
- This shows that our scheduler successfully combines Round-Robin with Priority-based ordering.

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**



1. **New**: [When we call `new Thread(process)`, but before calling the `.start()` method.]

2. **Runnable**: [When it is added to the `processQueue`.]

3. **Running**: [when the scheduler simulator calls `currentThread.start()` and the code inside the `run()` is being excuted]

4. **Waiting**: [when we use `Thread.sleep()` to simulate processing time, or when we use `currentThread.join()` to wait for P1 to finish its quantum.]

5. **Terminated**: [When `run()` method finishes and `remainingTime` reaches 0.]

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Web Server]

**Description**: 
[A server handling many people visiting a website at the same time.]

**Why Round-Robin works well here**: 
[It provides Fairness. Every user gets a small amount of CPU time, so no one has to wait too long, even if someone else is downloading a very large file.]

### Example 2: [PC Multitasking]

**Description**: 
[Running many apps at once, like VS code, Chrome, and Word.]

**Why Round-Robin works well here**: 
[It provides Responsiveness. The CPU switches between apps so quickly that they all seem to run at the same time.]

---

## Summary

**Key concepts I understood through these questions:**
1. Context Switching
2. Priority Scheduling
3. Thread Lifecycle

**Concepts I need to study more:**
1. Thread Library Methods
2. Thread Management
