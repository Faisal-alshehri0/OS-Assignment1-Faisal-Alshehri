# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

A process is an independent program with its own memory space, while a thread is a smaller unit of execution within a process that shares memory with other threads. Threads are faster to create and communicate more efficiently than processes. In this assignment, threads were used because they allow lightweight simulation of multiple processes running concurrently without the overhead of creating separate processes.

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

In my program, when a process does not finish within its time quantum, it is moved back to the ready queue. This can be clearly seen in the output.

Example from my output:
```"P1 yields CPU for context switch"
[[P3 → P4 → P5 → ... → P14 → P1]]
```

**Explanation of example:**
This demonstrates how the process returns to the end of the queue and waits for another turn. This behavior ensures fairness, as all processes get equal chances to use the CPU.

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

he thread lifecycle is demonstrated clearly in the program. A thread is created and then started using currentThread.start(), after which it begins execution in the run() method

1. **New**:P1 is in the New state when it is created using new Thread(process) inside the addProcessToQueue method, before start() is called.

2. **Runnable**:P1 becomes Runnable when currentThread.start() is called in the main loop, making it ready to be executed by the CPU.

3. **Running**: P1 is in the Running state when the run() method is executing, as shown in the output:
"P1 executing quantum [3000ms]"

4. **Waiting**: P1 enters the Waiting state during execution when Thread.sleep() is used to simulate processing time, which is reflected in the output:
"Quantum progress: [███████████████] 100%"

5. **Terminated**: P1 reaches the Terminated state when it finishes execution completely, as shown in the output:
"P1 finished execution!"

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: Web Server Handling Multiple Requests

**Description**: 
A web server handles multiple user requests at the same time, where each request is processed by a separate thread

**Why Round-Robin works well here**: 
Round-Robin ensures that each request gets a fair share of CPU time. This prevents one request from blocking others and improves responsiveness, especially when many users are accessing the server simultaneously.

### Example 2: Multimedia Application (Video Player)

**Description**: 
A video player uses multiple threads to handle audio, video playback, and user input at the same time.

**Why Round-Robin works well here**: 
Round-Robin allows each task (audio, video, input) to run for a short time slice, ensuring smooth playback and quick response to user actions. This improves user experience by preventing lag or freezing.

---

## Summary

**Key concepts I understood through these questions:**
1. 
2. 
3. 

**Concepts I need to study more:**
1. 
2. 
