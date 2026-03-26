# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID

**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully

**Challenges**: Had to install JDK first because javac wasn't recognized

**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable

**Time spent**: 30 minutes

---

## Your Development Log:

### Entry 1 - [March 26, 2026, 3:00 AM]
**What I did**: Environment Setup, Repository Initialization, and Code Analysis.

**Details**: 
- Created a GitHub account using my university email and forked the starter repository.
- Renamed the repository to OS-Assignment1-Abdulrahman-Alfalah and made it public.
- Connected VS Code to my GitHub account and installed the recommended extensions.
- Changed the studentID on line 150 of SchedulerSimulation.java to my actual ID (445052834).
- Read the entire 300 lines of the starter code to understand how the Round-Robin algorithm and Threads work.
- Watched the provided YouTube tutorials and read the Wikipedia pages for deeper understanding.
- Used AI tools to explain some complex parts of the code and to help troubleshoot environment issues.

**Challenges**: The code wouldn't run initially because I was using the "Code Runner" button directly, which couldn't find the main class or link the files together.

**Solution**: With the help of AI, I found two ways to fix this:
- Manual Way: Using the terminal command java -cp . SchedulerSimulation to tell Java exactly where to find the files.
- IDE Way: Using the small "Run" button that appears directly above the main method, which handles the setup automatically.
The simulation is now working perfectly

**Time spent**: 3 Hours

---

### Entry 2 - [March 26, 2026, 9:30 PM]
**What I did**: Implemented Feature 1 and upgraded the scheduler to Priority-Based Execution.

**Details**:
- I added a new variable called `priority` to the `Process` class to store a number from 1 to 5
- I used `random.nextInt(5) + 1` to give every new process a random priority.
- I updated the print message to show the priority
- **Important Change**: I noticed that the priority was just being generated and displayed but didn't change the order of execution (it was still FIFO).
  - To fix this, I changed the normal `Queue` to a `PriorityQueue`.
  - I wrote some code to compare two processes. This tells the program to put the process with the higher number (like 5) at the front of the line so it runs first.

**Challenges**: The program didn't know how to compare Threads by their priority because the priority number is inside the `Process` class.

**Solution**: 
- I used the `processMap` to help the program find the priority of each thread during the sorting process.
- I used AI tools to fully understand how to write the `PriorityQueue` comparator correctly.

**Time spent**: 2 Hours 

---

### Entry 3 - [Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

### Entry 4 - [Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

### Entry 5 - [Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

### Entry 6 - [Optional - Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

## Summary

**Total time spent on assignment**: [X hours]

**Most challenging part**: 

**Most interesting learning**: 

**What I would do differently next time**: 
