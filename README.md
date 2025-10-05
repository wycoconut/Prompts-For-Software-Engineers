# Prompts For Software Engineers
A list of useful prompts for Software Development purposes.

## 1. Code Generation Prompts

### Basic Code Generation (Zero-Shot Prompting)
```
You are an expert [programming language] developer. Write a function that [describe the task. Ensure the function is:

- Well-documented: Add clear comments explaining each step.
- Optimized for performance: Use efficient data structures and algorithms where applicable.
- Robust: Handle edge cases such as empty inputs, incorrect data types, and large datasets.
- Modular: Keep the function reusable and avoid hardcoded values.
```

### Optimized Code Generation (Few-Shot Prompting)
```
Here’s a basic implementation of [algorithm/function] in [programming language]:
[code snippet]

Now, improve this implementation by optimizing it using [optimization technique, e.g., memoization, dynamic programming, vectorization].

Explain:
- Why the optimized version is better in performance and efficiency.
- Time complexity improvements compared to the original.
- Any trade-offs
```

### Code Translation (Cross-Language Prompting)

```
Convert the following [source language] function into [target language]. Ensure that you:

- Maintain equivalent functionality in the new language.
- Explain key differences in syntax and behavior between the two languages.
- Highlight any necessary modifications due to differences in data types, function definitions, or execution models.
```

## 2. Debugging and Error Resolution

### Error Explanation and Fixes

```
I’m seeing this error in my [programming language] code:
[error message]

Explain:

- Why is this error occurring
- How to fix it - provide one or more solutions.
- Best practices to prevent similar errors in the future.
- For AI errors, you can also refer to our AI error library
```

### Bug Identification

```
Here’s a function that isn’t returning the expected output:
[code snippet]

Describe:

- Why the function is failing and identify the root cause
- How to fix it,
- Best practices to avoid similar bugs in the future
```

### Performance Optimization

```
Analyze the following [programming language] function and suggest optimizations to improve its [performance/memory usage/time complexity]:
[code snippet]

Provide:

- An explanation of the current inefficiencies and why they impact performance.
- A step-by-step optimization strategy, including specific improvements.
- A revised version of the function with the applied optimizations.
- A comparison of time complexity before and after optimization
```

## 3. Code Review and Best Practices

### Code Review for Best Practices

```
Review the following [programming language] function and suggest improvements for Readability, Performance, and Security
[code snippet]
```

### Security Vulnerability Detection

```
Analyze the following SQL query and identify potential security risks:
[SQL query]

Provide a safer alternative and explain why it’s secure.
```

## 4. Documentation and Explanation

### Generating Docstrings

```
Write a detailed docstring for the following [programming language] function:
[code snippet]

Make sure the docstring includes:

- A brief description of what the function does.
- Parameters with expected data types and descriptions.
- Return value with its type and meaning.
- Edge cases or exceptions the function may handle.
- Usage example (optional) to demonstrate correct usage.
```

## 5. AI for DevOps and Automation


### Dockerfile Generation

```
Generate a Dockerfile to containerize a [technology/framework] application with the following requirements:

- Use a lightweight and optimized base image.
- Ensure all required dependencies are copied and installed efficiently.
- Expose the necessary ports for the application.
- Use an appropriate CMD or ENTRYPOINT to start the application.
- Keep the image size minimal and follow best practices for security and performance.
```

### CI/CD Pipeline Configuration

```
Write a [CI/CD tool] workflow to automate the deployment of a [technology/framework] application to [deployment platform] with the following requirements:

- Runs on specific events (e.g., code push to main).
- Installs necessary dependencies and prepares the application for deployment.
- Deploy the application to [target platform] efficiently.
- Ensures minimal permissions, caching, and optimized build processes.
- Provides logging and alerts for failures.
```

## 7. Data Processing and Analysis

### Data Cleaning with Pandas

```
Write a Pandas script to clean and preprocess a dataset with the following steps:

- Remove duplicate rows efficiently.
- Fill missing values using an appropriate strategy (e.g., mean, median, or interpolation).
- Convert all column names to a consistent format (e.g., lowercase, snake_case).
- Save the processed DataFrame in a specified format (e.g., CSV, Parquet).
```


### SQL Query Optimization

```
Optimize the following SQL query for faster execution on a large dataset:
[SQL query]

Provide:

- Inefficiencies in the current query
- Optimized version of the query
- Explanation of performance improvements
- Best practices for writing efficient SQL queries on large dataset
```

---

# 12 Rules for Vibe Coding

1. Start with vibe PMing
2. Keep your tech stack simple
3. Give Al the right rules & documentation
4. Ask Al NOT to code
5. Ask Al for options and pick the simple one
6. Break tasks into small steps
7. Include images to give Al context
8. Test ruthlessly after every change
9. Don't hesitate to revert
10. Use Github for version control
11. Use your voice to feel the vibes
12. Ask Al to explain the code

[Credits To Peter Yang](https://creatoreconomy.so/p/12-rules-to-vibe-code-without-frustration)

---

# Design Inspiration Stack
https://mobbin.com/
https://designvault.io/
https://godly.website/

## Others
AppLaunchpad: App Store Screenshot Inspiration<BR>
Landingfolio: Landing page inspiration<BR>
Curated Design: Web UI Inspiration<BR>
Coolors: Color Inspiration<BR>
Logosystem: Logo Inspiration<BR>
Magritte: Social media Ad Inspiration<BR>

## UI / UX Case Studies of Good Websites
** Good resource if you intend to actually UNDERSTAND the reason behind each design decision
https://growth.design/case-studies

---

# Claude Docs (Prompt Library)
https://docs.claude.com/en/resources/prompt-library/library

- [Python bug buster](https://docs.claude.com/en/resources/prompt-library/python-bug-buster)
- [SQL Sorcerer](https://docs.claude.com/en/resources/prompt-library/sql-sorcerer)
- [Google apps scripter](https://docs.claude.com/en/resources/prompt-library/google-apps-scripter)
- [Git gud](https://docs.claude.com/en/resources/prompt-library/git-gud)
- [Code consultant](https://docs.claude.com/en/resources/prompt-library/code-consultant)
- [Function fabricator](https://docs.claude.com/en/resources/prompt-library/function-fabricator)
- [Code clarifier](https://docs.claude.com/en/resources/prompt-library/code-clarifier)
- [Efficiency estimator](https://docs.claude.com/en/resources/prompt-library/efficiency-estimator)
- [Data organizer](https://docs.claude.com/en/resources/prompt-library/data-organizer)
- [Spreadsheet sorcerer](https://docs.claude.com/en/resources/prompt-library/spreadsheet-sorcerer)
- [CSV Converter](https://docs.claude.com/en/resources/prompt-library/csv-converter)
- [Product naming pro](https://docs.claude.com/en/resources/prompt-library/product-naming-pro)


---

# Worth Reading

12 Rules to Vibe Code Without Frustration (Peter Yang)<BR>
https://creatoreconomy.so/p/12-rules-to-vibe-code-without-frustration

The Ultimate Vibe Coding Guide<BR>
https://www.reddit.com/r/ClaudeAI/comments/1kivv0w/the_ultimate_vibe_coding_guide/

BWAI PRD Creator (André Teow)<BR>
https://chatgpt.com/g/g-68235a9c5f8c8191875f682e6a6b4652-bwai-prd-creator

BWAI design system 2<BR>
https://chatgpt.com/g/g-686c02218e648191b32d13f562b60790-bwai-design-system-2

GoFullPage Chrome Extension<BR>
https://chromewebstore.google.com/detail/gofullpage-full-page-scre/fdpohaocaechififmbbbbbknoalclacl

Basic AI Prompts for Developers: Practical Examples for Everyday Tasks<BR>
https://portkey.ai/blog/basic-ai-prompts-for-developers/

ChatGPT - Prompts for Writing and Generating Codes<BR>
https://dev.to/techiesdiary/chatgpt-prompts-for-writing-and-generating-codes-59kf

ChatGPT - Prompts for Optimizing Code<BR>
https://dev.to/techiesdiary/chatgpt-prompts-for-optimizing-code-3kkg

ChatGPT - Prompts for developers<BR>
https://dev.to/techiesdiary/chatgpt-prompts-for-developers-216d

John Rush - Compilation of 61 AI Coding Agents & IDEs and tested all of them<BR>
https://x.com/johnrushx/status/1958363431922500053?t=_46afiJZuXcRwvFcqLJ7WQ&s=19

GitHub Copilot with VS Code<BR>
https://medium.com/@bobmain49/github-copilot-with-vs-code-here-we-go-d9dd29512866

---

# Tools

## Gemini Code Assist<BR>
[VSCode Extention](https://marketplace.visualstudio.com/items?itemName=Google.geminicodeassist) | [Video Walkthrough](https://www.youtube.com/watch?v=W1JxFwh5EGA) | [Official Guide](https://developers.google.com/gemini-code-assist/docs/write-code-gemini) | [How to Prompt Gemini Code Assist](https://www.youtube.com/watch?v=Jr2nze3bwd4) | [Learning Lab](https://www.cloudskillsboost.google/catalog_lab/31671)

Free with Personal Google Account.

The "Gemini Code Assist for individuals" edition, which is the free tier, has very generous usage limits designed to support active individual developers.

Free tier:
* **Code Completions:** Up to **180,000 completions per month**.
* **Chat Requests:** Up to **240 chat requests daily**.
* **Code-Related Requests (General):** A limit of **6,000 code-related requests daily**.
* The free tier **does not expire**.
* It is accessed with a personal Google Account (not associated with Cloud Identity or Google Workspace).


## Gemini CLI (Command Line Interface)
[Website](https://google-gemini.github.io/gemini-cli/) | (GitHub](https://github.com/google-gemini/gemini-cli)

Free tier:
* **Model Requests:** Up to **1,000 requests per day** and **60 model requests per minute**.


----

# Notable Git Repositories:

DEV ChatGPT Prompts<BR>
https://github.com/PickleBoxer/dev-chatgpt-prompts
