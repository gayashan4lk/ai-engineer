# Engineering Habits

> ~10 min read · For: Years 1–2, and before your internship · Last reviewed: September 2026

**TL;DR**

- The gap between a student who can code and a junior engineer a team wants is mostly **habits**: Git, testing, debugging, reading code and communicating.
- AI makes these habits **more** important. When code is cheap to produce, the value is in checking it, reviewing it and keeping it maintainable.
- Start using professional habits in your coursework now. By your internship they should feel normal, not new.

---

## Why habits matter

Most university assignments are written by one person, run once, graded, and never touched again. Real software is written by a team, changed hundreds of times over years, and run by people who didn't write it.

That difference is why employers care so much about habits. On your first day at work, nobody will check whether you can reverse a linked list. They'll check whether you can pull the code, understand it, make a small change safely, and get it reviewed.

AI changes this in one important way. It produces code faster than anyone can review it. **Teams that use AI well lean even harder on tests, reviews and clean Git history**, because those are the safety nets that catch "almost right" code before users do.

---

## 1. Git, properly

Everyone lists Git on their CV. Far fewer use it well.

**The habits:**

- **Commit small and often.** One logical change per commit. If your message needs the word "and", it's probably two commits.
- **Write useful commit messages.** Start with a short summary in the imperative mood ("Add login rate limiting"), then explain *why* if it isn't obvious.
- **Work on branches** and merge through pull requests, even on solo projects. It builds the habit, and it gives you a place to review your own changes.
- **Understand what Git is doing:** commits, branches as pointers, merge vs rebase, and what `HEAD` means. Then you can recover from mistakes instead of deleting the folder and cloning again.
- **Never commit secrets.** Use `.gitignore` and environment variables. Removing a leaked API key from Git history is painful, and bots scan public repos for keys within minutes.

## 2. The command line

Graphical tools are fine, but production servers, CI pipelines, containers and many AI coding agents all live in the terminal.

**The habits:** navigate and edit files from the shell, use pipes (`|`) and `grep` to search output, read logs with `tail -f`, manage processes, and write a small shell script when you catch yourself repeating commands.

## 3. Debugging with a method

Beginners debug by changing things at random until the error disappears. Engineers debug with a method:

1. **Reproduce it.** Get a reliable way to make the bug happen.
2. **Read the error.** The whole message and stack trace, slowly. It usually tells you where to look.
3. **Form a hypothesis.** "I think `user` is `null` here because the query returned nothing."
4. **Test the hypothesis.** Use a debugger, a log line or a small experiment. Change one thing at a time.
5. **Narrow it down.** Cut the problem in half repeatedly: which half of the code, which commit (`git bisect`), which input?
6. **Fix it, and prove it.** Write a test that fails before your fix and passes after it.

Learn to use a real **debugger** in your editor, with breakpoints, stepping and watching variables. It's faster than print statements for anything non-trivial, and many students never try one.

## 4. Testing

**Tests are how you know your code works, and how you know it still works after someone changes it.** That someone might be you in six months, a teammate, or an AI agent.

**The habits:**

- Write **unit tests** for logic. Start with the normal case, then edge cases: empty input, very large input, invalid data.
- Understand the difference between unit, integration and end-to-end tests, and why teams need all three.
- **Run tests before every push.** Better still, set up continuous integration (for example, GitHub Actions) so they run automatically.
- When you fix a bug, **add a test that would have caught it.**

A simple rule for the AI era: **never merge AI-generated code that isn't covered by tests you understand.**

## 5. Reading code

You'll spend more time reading code than writing it, both other people's and AI's.

**The habits:** start from the entry point (`main`, the route handler, the test) and follow the flow. Use "go to definition" and "find references" in your editor. Read the tests to learn what the code is *supposed* to do. Draw a quick diagram of how the main parts connect.

Practise by reading real open-source projects in your main language. Pick one you use and trace how a single feature works from start to finish.

## 6. Code review

**Receiving review:** treat comments as information, not criticism. Ask questions when you don't understand, and thank people for catching things.

**Giving review:** check that the code does what it claims, handles errors, has tests, and is readable. Point out problems kindly and specifically ("This loop runs a query per item. Could we fetch them all at once?").

Review **your own** pull request before asking anyone else. You'll catch half the issues yourself.

## 7. Writing things down

Engineers write constantly: READMEs, pull request descriptions, design notes, bug reports and messages asking for help.

**The habits:**

- Every project gets a **README** saying what it does, how to run it, and how it's structured.
- A good **pull request description** says what changed, why, and how you tested it.
- When asking for help, include **what you're trying to do, what you tried, what happened and what you expected**. People help those who make helping easy.

In Sri Lanka's export-focused industry, where you'll often work with overseas teammates and clients, clear written English is a professional skill in its own right.

---

## Where AI fits

- **Use AI for:** explaining an unfamiliar Git situation, suggesting test cases you missed, a first review of your own pull request, drafting a README you then edit, and explaining code you're reading.
- **Go AI-free for:** learning Git's model (use visual tools like the one below), your first attempts at debugging, and deciding *what* to test. AI can write test code well. Choosing what matters to test is your job.
- **Be careful:** AI suggests confident Git commands, including destructive ones like `reset --hard` or `push --force`. Understand any command before you run it.

See [Learning with AI](02-learning-with-ai.md) for the full playbook.

---

## Do this next

- [ ] Put **every** coursework project in a Git repository with small, well-described commits.
- [ ] Finish the Learn Git Branching exercises until you can explain merge vs rebase.
- [ ] Set up a debugger in your editor and use it on your next bug.
- [ ] Add unit tests to one existing project, aiming for the main logic rather than 100% coverage.
- [ ] Write a proper README for your best project.
- [ ] Pick one open-source project in your main language and trace one feature through the code.

---

## Build this

1. **Test your old project (small).** Take a past assignment and add a test suite. Find at least one bug in the process (there's almost always one). Fix it with a failing test first.
2. **Add CI (medium).** Add a GitHub Actions workflow to one repository that runs your tests and a linter on every push and pull request. Add a status badge to the README. It's a small thing that immediately looks professional.
3. **Team project done properly (stretch).** With two or three classmates, build something small using real team practices: an issue board, branches, pull requests with reviews, CI, and a shared README. Protect the main branch so nobody can push to it directly. This is closer to real work than almost any assignment.

---

## Sri Lanka notes

- Group assignments are common in Sri Lankan degree programmes. Use them to practise branches, pull requests and reviews rather than emailing zip files or sharing one laptop.
- Interns who arrive already comfortable with Git, pull requests and writing tests get trusted with real tasks faster. Most interns don't, so this is an easy way to stand out.
- Internship managers often say that communication, such as asking questions early and giving status updates, matters as much as technical skill. Practise it in group projects.

---

## Free resources

- [Pro Git (book)](https://git-scm.com/book/en/v2): the complete, free guide to Git.
- [Learn Git Branching](https://learngitbranching.js.org/): an interactive visual tutorial for how branches, merges and rebases really work.
- [How to Write a Git Commit Message](https://cbea.ms/git-commit/): the classic short guide.
- [The Missing Semester of Your CS Education (MIT)](https://missing.csail.mit.edu/): the shell, Git, debugging and editors.
- [Google Engineering Practices: Code Review](https://google.github.io/eng-practices/review/): how reviewers and authors should approach code review.
- [Julia Evans' blog](https://jvns.ca/): friendly, clear writing on debugging, the command line, Git and networking.

---

**Read next:** [Fundamentals that still matter](01-fundamentals-that-still-matter.md) · [The landscape](../00-the-landscape.md)
