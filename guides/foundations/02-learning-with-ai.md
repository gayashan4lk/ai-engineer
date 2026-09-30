# Learning with AI: Use It, But Learn First

> ~10 min read · For: everyone, from Year 1 · Last reviewed: September 2026

**TL;DR**

- AI can make you *finish* faster while you *learn* less. There is now controlled evidence for this, and the biggest loss is in **debugging**.
- The fix is not to avoid AI. Use it as a **tutor, not a vending machine**: attempt first, ask for explanations rather than answers, and practise regularly without it.
- Watch for the warning signs: you can't explain your own code, you can't start without AI, or your debugging method is pasting in the error.

---

## The evidence

In early 2026, Anthropic ran a randomised controlled trial with developers learning a Python library they had never used ([Anthropic, 2026](https://www.anthropic.com/research/AI-assistance-coding-skills)). Half could use an AI assistant and half coded by hand. Afterwards, everyone took a short quiz on the concepts they had just used.

- The AI group scored **17% lower** (about 50% against 67%). That is close to two letter grades.
- The AI group was **not significantly faster**.
- The largest gap was on **debugging questions**: understanding when code is wrong and why it fails.
- Not everyone in the AI group did badly. The people who scored well used AI to **understand**: they asked follow-up questions, requested explanations and asked conceptual questions while they wrote the code themselves.

That last point matters most. The tool didn't decide the outcome. **How it was used** did.

Harvard's CS50, one of the world's largest intro programming courses, reached the same conclusion from the teaching side. It gives students an AI tutor, the [CS50 Duck](https://cs50.ai/), that is deliberately built to **lead students towards answers instead of handing them over** ([Liu et al., SIGCSE 2024](https://cs.harvard.edu/malan/publications/V1fp0567-liu.pdf)). If one of the best-known CS courses thinks the default chatbot behaviour is bad for learning, take that seriously.

---

## Why this happens

Learning needs **effort at the right moment**. When you're stuck and push through, your brain builds a model of how the thing works. When an answer shows up instantly, you get the result without the model.

Think of AI like a lift in a gym. It gets you to the top floor faster, but if the goal was to build leg strength, you just skipped the workout.

This matters more in software than in most fields because of the "almost right" problem. Developers say AI output is often close to correct but subtly wrong ([Stack Overflow, 2025](https://survey.stackoverflow.co/2025/ai)). **You can only catch "almost right" if you know what "right" looks like.** That knowledge comes from the workouts you might be tempted to skip.

---

## The playbook

### 1. Attempt first

Before asking AI anything, **try on your own for 15–30 minutes**. Read the error. Form a guess. Check the documentation. Add a print statement.

You will often solve it. When you don't, your question to the AI will be much better, because you'll know what you tried and where you're stuck.

### 2. Tutor mode, not answer mode

Tell the AI how you want it to help. Here is a prompt you can reuse:

```text
I'm a student learning <topic>. I want to understand this myself.
Don't give me the full solution or write the code for me.
Instead:
- Ask me what I've tried and what I think is wrong.
- Give me one hint at a time, starting small.
- If I ask "why", explain the concept, not just the fix.
Here is my problem and my attempt: ...
```

Good questions to ask in tutor mode:

- "What concept do I need to understand to solve this?"
- "What's wrong with my reasoning here?" (after explaining your reasoning)
- "Give me a smaller example of the same idea."
- "What would a senior engineer check first?"

### 3. Predict before you run

Before running code, whether yours or AI's, **predict what it will do**. Write your prediction down if you like. Then run it. When you're wrong, you've found a gap in your understanding, and that is the most valuable moment in learning.

### 4. Explain it back

After AI helps you, close the chat and **explain the solution in your own words**: out loud, in a comment, or in your learning log. If you can't, you haven't learned it yet. Ask the AI to quiz you on it:

```text
Quiz me with 5 short questions on what we just discussed.
Don't give answers until I've replied to each one.
```

### 5. Retype, don't paste (while learning)

When you're learning something new, **type out** AI-suggested code rather than pasting it, and change something as you go: rename variables, restructure it, or add a check. It is slower, and that is the point. Once you've mastered a pattern, paste freely.

### 6. Do regular AI-free practice

Set aside time to work with **no AI at all**:

- The first time you meet a new concept (recursion, pointers, SQL joins, async).
- Practice problems and exercises.
- **Debugging practice.** This is the skill that suffers most.
- Anything that will be tested without AI: exams, many technical interviews and online assessments.

A simple rule: **if you'll need to do it without AI later, practise it without AI now.**

### 7. Use AI where it really helps learning

AI is excellent at many learning tasks. Use it for these freely:

- Explaining an error message **after** you've read it yourself.
- Explaining a concept several different ways until one clicks.
- Generating practice questions, quizzes and small exercises.
- Reviewing code *you* wrote: "What would you improve here, and why?"
- Giving you a tour of an unfamiliar codebase.
- Summarising long documentation so you know where to look (then read the actual docs).

---

## Warning signs of over-reliance

Be honest with yourself. If several of these are true, rebalance:

- You can't explain how your own project works.
- You feel unable to *start* anything without opening an AI chat.
- Your first reaction to an error is to paste it into AI, before reading it.
- You pass assignments but struggle in exams or practical tests.
- You couldn't rebuild last month's project without AI.
- You accept AI output you don't understand because "it works".

*My opinion:* heavy reliance also quietly erodes **confidence**. You start to believe you can't do it alone, and that belief shows in interviews. The fix is small, regular doses of doing it yourself.

---

## Academic integrity

Every university and module has its own AI policy, and they vary. **Read the policy for each module and follow it.** If it's unclear, ask your lecturer.

Beyond the rules, think about who you're cheating. A submitted assignment is worth a few marks. The understanding behind it is what gets you through a technical interview and your first year of work. Handing in AI work you don't understand trades something valuable for something cheap.

---

## Where AI fits

- **Use AI for:** explanations, hints, quizzes, code review of your own work, exploring unfamiliar code, and speeding up things you have already mastered.
- **Go AI-free for:** first contact with a new concept, practice problems, debugging practice, and anything assessed without AI.
- **Why:** the evidence shows the *way* you use AI decides whether you learn. Asking "why" builds skill. Asking "give me the code" mostly doesn't.

---

## Do this next

- [ ] Save the tutor-mode prompt above in your notes and use it for a week.
- [ ] Pick one AI-free block per week, such as 2 hours every Saturday, and protect it.
- [ ] For the next five bugs you hit, spend 15 minutes on each before asking for help.
- [ ] After each AI-assisted session, write two sentences in your learning log explaining what you learned.
- [ ] Read your university's and your modules' AI-use policies.
- [ ] Choose one past project and check you can explain every file in it. Relearn any part you can't.

---

## Build this

1. **Rebuild without AI (small).** Take a small project you built with heavy AI help and rebuild it from scratch without AI. Note every place you got stuck. That list is your study plan.
2. **Your own tutor bot (medium).** Build a simple chat app that calls an LLM API with a system prompt enforcing tutor-mode rules: no full solutions, one hint at a time. Test it on real homework-style questions and see if it holds its rules. You'll learn about prompts, APIs and the limits of both.
3. **Teach it (stretch).** Write a blog post or record a 5-minute video explaining a concept you recently learned, such as how a hash map works or what an index does in SQL. Teaching is the strongest form of explaining it back, and it doubles as portfolio material.

---

## Sri Lanka notes

- Many Sri Lankan students study in English as a second language. AI is a great way to **understand dense English documentation**: ask it to explain a paragraph more simply or in Sinhala or Tamil. Then go back and read the original. Your English technical reading will improve, and that matters at work.
- Paid AI plans are expensive in rupees. The free tiers of major AI assistants and education offers (look for student programmes from the major tool providers) are more than enough for learning.
- Many local companies run practical assessments or live coding for interns. Those are exactly the situations where AI-free practice pays off.

---

## Free resources

- [How AI assistance impacts the formation of coding skills (Anthropic)](https://www.anthropic.com/research/AI-assistance-coding-skills): the study discussed above.
- [CS50.ai](https://cs50.ai/): Harvard's free AI tutor, built to guide rather than give answers. Try it with the free [CS50x](https://cs50.harvard.edu/x/) course.
- [Teaching CS50 with AI (paper)](https://cs.harvard.edu/malan/publications/V1fp0567-liu.pdf): how and why CS50 limits what its AI will do.
- [Learning How to Learn (Coursera, free to audit)](https://www.coursera.org/learn/learning-how-to-learn): the science of effective study, useful with or without AI.
- [Exercism](https://exercism.org/): free coding exercises in 70+ languages with optional human mentoring, ideal for AI-free practice.

---

**Read next:** [Fundamentals that still matter](01-fundamentals-that-still-matter.md) · [Engineering habits](03-engineering-habits.md)
