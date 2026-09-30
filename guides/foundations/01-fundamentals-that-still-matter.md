# Fundamentals That Still Matter

> ~10 min read · For: Years 1–2, and anyone preparing for interviews · Last reviewed: September 2026

**TL;DR**

- AI can generate code, but it can't make you able to **check** that code. Fundamentals are how you catch the "almost right" answer.
- You don't need to master all of computer science. You need a **working understanding** of about eight areas, enough to explain what your code does and why it fails.
- The test for each area is simple: **can you predict, explain and debug it without AI?**

---

## Why fundamentals matter more now, not less

A common idea goes: "AI writes the code now, so why learn how things work underneath?" It gets things backwards.

When AI writes code, **your job becomes judging it**. Is this query going to be slow with a million rows? Will this code break when two users click at the same time? Is this API call leaking a secret? AI will answer these questions confidently, and sometimes wrongly. Only fundamentals let you tell the difference.

Developers report that AI output is often "almost right, but not quite", and that debugging it takes time ([Stack Overflow, 2025](https://survey.stackoverflow.co/2025/ai)). A controlled study found that people who learned with AI did worst on **debugging** questions ([Anthropic, 2026](https://www.anthropic.com/research/AI-assistance-coding-skills)). Debugging is fundamentals in action. It's where you use your mental model of how a computer, a network or a database actually behaves.

Fundamentals are also what **interviews test**, because they can't be faked in a live conversation.

---

## The eight areas, and what "enough" looks like

Your degree covers most of these. The goal is not a perfect grade. It is to be able to **use** each one when reading and debugging real code.

### 1. One programming language, properly

Pick one mainstream language, such as Python, Java, JavaScript/TypeScript, C# or Go, and go deep before going wide.

**Enough looks like:** you know how its types, errors, memory model (references vs values) and standard library work. You can write a 200-line program without looking up basic syntax. You can read an unfamiliar codebase in it.

### 2. Data structures and algorithms

Arrays, hash maps, sets, stacks, queues, trees, graphs, sorting and searching, and Big-O thinking.

**Enough looks like:** you can pick the right structure for a problem and explain why. You can spot when a nested loop turns a fast program into a slow one. You can solve typical easy and medium interview problems.

### 3. How a computer runs your program

Memory (stack vs heap), processes and threads, concurrency, files and I/O, and what the operating system does.

**Enough looks like:** you can explain a race condition, why a program runs out of memory, and the difference between CPU-bound and I/O-bound work.

### 4. Networks and the web

HTTP (methods, status codes, headers), DNS, TCP vs UDP, TLS/HTTPS, REST APIs, and what happens when you type a URL into a browser.

**Enough looks like:** you can debug a failing API call using the browser's network tab or `curl`. You know what a 401, 403, 404 and 500 each suggest.

### 5. Databases

SQL (joins, grouping, subqueries), indexes, transactions, normalisation, and when to use a document or key-value store instead.

**Enough looks like:** you can write a join without looking it up, explain why a query is slow, and say what an index costs as well as what it gains.

### 6. Linux and the command line

Navigating files, permissions, processes, environment variables, pipes, and basic shell scripting.

**Enough looks like:** you can SSH into a server, find a log file, search it with `grep`, and restart a service. Most production systems run on Linux.

### 7. Security basics

Authentication vs authorisation, hashing passwords, SQL injection, XSS, secrets management, and the OWASP Top 10 at a high level.

**Enough looks like:** you can spot an injection risk or a hard-coded API key in a code review, **especially in AI-generated code**, which often contains both.

### 8. Software design

Functions and modules with one clear job, separation of concerns, basic object-oriented and functional ideas, and a few common patterns.

**Enough looks like:** you can explain why one version of some code is easier to change than another, and you can split a big function into sensible pieces.

---

## How to actually learn them

**Build the thing to understand the thing.** Reading about hash maps teaches you less than implementing one. Reading about HTTP teaches you less than writing a tiny server with a raw socket. Each area above has a "build it yourself" exercise in [Build this](#build-this) below.

**Connect lectures to practice.** When your OS module covers threads, write a program with a race condition and fix it. When your database module covers indexes, create a table with a million rows and time a query before and after adding an index. A lecture concept becomes real when you've seen it happen on your own machine.

**Use the three-question test.** For any concept, ask yourself:

1. Can I **predict** what will happen before I run it?
2. Can I **explain** it simply to a first-year student?
3. Can I **debug** it when it goes wrong, without AI?

If you answer "no" to any of these, that's your next thing to study.

**Space it out.** Revisit topics a few weeks later. Fundamentals fade if you only touch them the week before an exam.

---

## Where AI fits

- **Use AI to:** explain a concept in different ways, create practice problems at your level, check your explanation ("Is this how a B-tree index works? Correct me."), and visualise things such as "show me step by step how this sorting algorithm processes [5, 2, 8, 1]".
- **Go AI-free for:** implementing data structures, solving practice problems, and your first attempt at any "build it yourself" exercise. The point of these exercises is the struggle.
- **Be careful:** AI explanations of fundamentals are usually good, but it can mix up details, especially about performance and concurrency. When something matters, confirm it in a textbook or official documentation.

See [Learning with AI](02-learning-with-ai.md) for the full playbook.

---

## Do this next

- [ ] Choose your **main language** and commit to it for the next six months.
- [ ] Rate yourself 1–5 on each of the eight areas with the three-question test. Circle the two weakest.
- [ ] Start one "build it yourself" exercise from the list below this week.
- [ ] Solve **two** data structure or algorithm problems a week without AI, and review your solutions afterwards (AI review is fine *after* you've finished).
- [ ] Install Linux, or use WSL on Windows, and do your coursework from the terminal for a month.
- [ ] For your next database assignment, check query performance with `EXPLAIN`.

---

## Build this

1. **Build your own data structures (small).** Implement a dynamic array, a hash map with collision handling, and an LRU cache in your main language. Write tests for each. Then compare their speed with the built-in versions.
2. **HTTP server from scratch (medium).** Using only sockets, with no web framework, write a server that handles `GET` requests and returns static files. Then make it handle several clients at once with threads, and fix the bugs you create. This one project touches networking, concurrency, files and error handling.
3. **Mini database (stretch).** Build a tiny key-value store that saves to disk, supports `get`, `set` and `delete`, and survives a crash (write to a log before updating). Add a simple index. It's the best way to understand why real databases are designed the way they are.

---

## Sri Lanka notes

- Local interviews and internship assessments commonly include **OOP concepts, basic data structures, SQL queries and problem-solving**, often as a written test or a short coding task. Strong fundamentals cover most of these.
- Your university modules are more useful than they may seem. The students who stand out are the ones who connect lecture topics to things they have built.
- If your programme doesn't cover an area well, often Linux or security, fill the gap with the free resources below.

---

## Free resources

- [CS50x (Harvard)](https://cs50.harvard.edu/x/): the best free introduction to programming and computer science fundamentals.
- [Teach Yourself Computer Science](https://teachyourselfcs.com/): a curated self-study path through the core CS subjects, with free book and lecture choices for each.
- [Operating Systems: Three Easy Pieces](https://pages.cs.wisc.edu/~remzi/OSTEP/): a free, readable OS textbook covering processes, memory and concurrency.
- [CMU 15-445 Database Systems](https://15445.courses.cs.cmu.edu/): free lectures on how databases work inside.
- [Beej's Guide to Network Programming](https://beej.us/guide/bgnet/): sockets from the ground up, ideal for the HTTP server project.
- [The Missing Semester of Your CS Education (MIT)](https://missing.csail.mit.edu/): the shell, Git, debugging and other tools universities often skip.

---

**Read next:** [Learning with AI](02-learning-with-ai.md) · [Engineering habits](03-engineering-habits.md)
