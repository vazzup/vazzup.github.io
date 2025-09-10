---
date: '2025-09-09T19:58:10+05:30'
draft: false
title: 'Building With Claude Code'
tags: ['startups', 'AI', 'building', 'Claude', 'lessons', 'tips']
categories: ['startups', 'tips', 'software development']
---
Claude Code is awesome. If you're a software developer, using it is a superpower. It's effectively a junior SDE on your
payroll, and you're its Engineering Manager. If you guide it well, it'll get everything you need done. I've been using
it for the last 3 weeks, and I have a lot of lessons to share. Let's begin:
   
### Managing Context is 50% of your job
Claude code can't change anything without context on your project and code. The thing is, it also can't really tell which
files are important context and which ones aren't. It uses heuristics to look for possibly relevant files, and in the 
process, fills up the context window really quickly.   
   
Do these three things:
1. Point it to specific files that you want it to read. Even better, point it to specific functions in files
2. Use the double escape trick to go to a base version of the context. When you press the escape button twice, you can 
go to a previous command. By undoing a few commands, you also go back to the context from before that command. Let's 
say you are working on the login product. There's a bug you've noticed. You can point it to the bug & get it to fix it.
Once done, just double escape and go back to the previous context. The context of the bug won't help further development
anyway since it's independent of the product being built.
3. Document everything between sessions and after features. I find a good way to end a session is to ask it to document 
key learnings / context in a markdown document at the end of the session. This way, when you start a new session, you can
just feed it that document and get it started.
   
### Create a plan in markdown first.
One of my favourite takes on how to plan an AI led project is this 
(workflow)[https://www.youtube.com/live/ZWS8XkNDyt0?si=3HxEKlXXa6zQ-YVX] shared by a Gauntlet student. It gives some 
really good prompts on planning a project with Claude Code. You should try to plan out what you build 
phase-by-phase. Document every step of the development up ahead, before you write a piece of code. Plan everything 
from the tech stack, to the design themes, development rules (linting, style guide) etc. That way, you can feed these
docs as context and know that Claude will know how to write your code. And planning upfront, breaking it down into phase 
helps bring order to the chaos; sort of like sprints. 
   
### Over-use the plan mode
Claude code comes with a plan mode where it first tries to plan out everything it needs to do to solve a problem, and then
asks you for the go-ahead to execute it. This is a far better way to write code than to just prompt it "do xyz". The reasons:
1. Planning ensures it's not meandering to find a solution. There's a clear path to solving the problem. This saves you
tokens and time. You also get a chance to correct it if you're wrong. If you think it's approaching the problem in a wrong
way, you can ask it to change plans based on your feedback. Give the go-ahead only when you're satisfied.
2. The plan mode uses Haiku which is also a lighter model and hence saves you token. No more sonnet / opus tokens wasted on
meandering through the space of possible solutions.
3. Most importantly, you get to manage Claude better. This is a chance to ensure that the proposed solution has a high 
probability of succeeding. It also helps you make sure Claude doesn't overengineer things (which it is very prone to).

I like to use the plan mode with --dangerously-skip-permissions mode. You plan it out with Claude, and then 
let it do its own thing.   
   
### Keep a grasp on the code
If you don't know what's in the code, you won't be able to prompt it well. You won't be able to point it to the right 
context either. You need to read the code, understand the project structure. Vibe coding doesn't work. You're gonna need
this especially for identifying some mean bugs. You will have to understand and guide it to the specific area of the bug.
Without that, Claude just gets lost in a large project with thousands of lines of code.   
   
### Test Driven Development is the way to gonna
Write tests yourself, or use another LLM to write tests for the code and expected behaviour. I'm talking Unit tests, 
integration tests, coverage, the works. You can use these tests as a measure of how well the code works. You may also give 
passing tests as a goal to Claude. That way, it works hard to pass tests, and hence writes code per your specification.
   
Pro-tip: Also force it to comment everything it writes. Documentation helps Claude with context in the future. 
   
Another pro-tip: When you're giving it code to review or find bugs in, tell it that the code was written by another 
engineer. It has a strong bias towards code it writes itself and can't be critical. If it thinks someone else wrote it, 
Claude gets critical and finds the smallest of bugs
   
Hope this helps, happy coding!

