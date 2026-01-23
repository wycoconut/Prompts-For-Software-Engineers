# How To Improve the Developer Experience when Coding With AI

Source : [Addy Osmani on LinkedIn](https://www.linkedin.com/posts/addyosmani_ai-programming-softwareengineering-activity-7420197342873735168-xmGX)

<img width="1456" height="813" alt="image" src="https://github.com/user-attachments/assets/a5785f8b-1d69-42c4-973f-d02134a8fb8b" />
** DX = Developer Experience, SWE = Software Engineers

## My AI coding workflow in 2026

Write-up: https://addyosmani.com/blog/ai-coding-workflow/

I get asked about my workflow for coding with LLMs pretty often so I thought I would share some notes on what works well for me. <BR>

Here is my 5-step workflow for this year:

1. **Specs before code (The "15-Minute waterfall")**

Don't dive straight into generating code - plan. I start by brainstorming with the AI to create a comprehensive [spec.md](https://github.com/wycoconut/Prompts-For-Software-Engineers/new/main#example-of-a-specmd) and a step-by-step project plan. You can use [this prompt](PRD-Prompt.md) to help you put something together.

We define requirements, UX, and edge cases before a single line of code is generated. Really improves quality. Cursor, Cline, Claude Code and many tools now encourage more planning before acting to support this workflow.

2. **Context is king - without it, LLMs can make incorrect assumptions.**

LLMs are only as good as the information you feed them. I use "context packing" - dumping relevant docs, existing patterns, and constraints into the session or project directory (using tools like gitingest or Context7). Don't make the AI guess or waste tokens trying to figure out what's in your head.

3. **Manage task granularity - just like with traditional engineering, do work in well defined tasks or chunks, not all at once.**

Break work into iterative chunks. "Implement one function/component" works infinitely better than "Build this app." I use a structured prompt plan, executing tasks one by one to keep the model on the rails. 

4. **Review and test what's important - LLMs are often an "over-confident pair programmer"**

It's healthy to treat AI output like code that came from an over-confident pair developer. It might look right, but is it? Review and test everything important. I weave testing into the loop - generating tests alongside the code and refusing to merge until they pass. If testing feels too much for your project (maybe it's a personal project), at least review the diffs. 

5. **Git is your save point - commit early and often.**

When an AI hallucinates or breaks the build (and it will), you need granular commit history to roll back to a safe state immediately. I've had so many experiences where I feel great 3 prompts in then the next 2 completely go off the rails. Tools increasingly support the idea of checkpoints and rollbacks, but for most workflows, just using git + committing can get you far.

In terms of models and tools: I have a core set of models (incl Gemini 3) and tools that I rely on pretty regularly, but I make time each week to try out what's new (patterns, open-source projects etc). 

So if the [Ralph Wiggum loop](https://blog.devgenius.io/ralph-wiggum-explained-the-claude-code-loop-that-keeps-going-3250dcc30809), [Gastown/Beads](https://steve-yegge.medium.com/welcome-to-gas-town-4f25ee16dd04) or other ideas trend they're on my radar and I can choose whether they make sense for my workflow. I'm very big on orchestration right now and use CLIs for more complex local work. It's very much just continuous learning + trying things.

AI tools are incredible force multipliers, but they don't replace the need for engineering fundamentals. In fact, they reward them. The human engineer remains the director of the show.

## Example of a spec.md

```
# Specification: Task Management App

## 1. Objective
Create a simple web application to manage a user's daily to-do list.

## 2. Features
- User can view a list of tasks.
- User can add a new task (title + description).
- User can mark a task as completed.
- User can delete a task.

## 3. Tech Stack
- Frontend: React (TypeScript)
- Backend: None (Use local storage for persistence)
- Styling: Tailwind CSS

## 4. User Stories
- **As a user**, I want to add a task so I don't forget it.
- **As a user**, I want to check off tasks to feel productive.

## 5. Data Model
```typescript
interface Task {
  id: string;
  title: string;
  description: string;
  completed: boolean;
  createdAt: Date;
}
```

