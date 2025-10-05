# AI Prompts Strategies

## 1. Q&A Prompt Strategy

### When To Use It:
When you have half-baked solutions that missed critical requirements.<BR>
The Q&A strategy flips the script — instead of the AI rushing to give you an answer, you force it to ask clarifying questions first.<BR>
It’s like pair programming with someone who doesn’t jump to conclusions.

### How It Works:
1. You present your initial problem or request
2. Instead of trying to solve it right away, the AI asks relevant questions to clarify requirements
3. You provide additional details based on these questions
4. The AI uses this enhanced context to deliver a more tailored solution.

### Benefits:
- Avoids assumptions that might lead to incorrect solutions
- Surfaces requirements you might not have thought to mention
- Creates more accurate and useful responses
- Establishes a collaborative problem-solving approach

### Example Use Case:

Instead of writing:

```
Help me create a user authentication system
```

Use the Q&A strategy:

```
I need to build a user authentication system for my web application.
Before providing a solution, please ask me relevant questions about
my specific requirements and constraints so you can give me the most appropriate implementation advice.
```

The AI might then ask questions like:

- What type of application is this (mobile, web, desktop)?
- What programming language and framework are you using?
- Do you need features like password reset, social login, or multi-factor authentication?
- What are your security requirements?
- Are there any specific compliance standards you need to follow?
- This exchange helps the AI understand exactly what you need before providing code or architecture recommendations, resulting in a more useful solution.

---

## 2. Pros and Cons Prompt Strategy

### When To Use It:
When you need a balanced assessment of both approaches for a specific situation.<BR>
Useful for assiting in making technical decisions.

### How It Works:
1. You present a decision point or choice between multiple options
2. You explicitly ask the AI to analyze each option’s strengths and weaknesses
3. The AI provides a balanced assessment of each option
4. You gain a clearer understanding of tradeoffs to make better decisions

### Benefits:
- Prevents one-sided recommendations
- Forces consideration of potential downsides
- Provides a structured comparison framework
- Helps avoid costly mistakes by considering limitations upfront
- Reveals factors you might not have considered

### Example Use Case:
Instead of asking:

```
What database should I use for my application?
```

Use the Pros and Cons Strategy:

```
I’m developing a product catalog application that needs to store product information, images, and customer reviews.
Please analyze the pros and cons of using MongoDB, PostgreSQL, and Firebase for this application.
Consider factors like scalability, query capabilities, ease of development, and maintenance requirements.
```

The AI might respond with an analysis like:

MongoDB:

Pros:
- Flexible schema for evolving product attributes
- Good performance for read-heavy operations
- Easy to scale horizontally
- Native JSON structure matches application data

Cons:
- Less robust for complex transactions
- Not ideal for highly relational data
- Potentially higher storage requirements
- Learning curve if team is primarily SQL-focused

PostgreSQL:

Pros:
- Strong ACID compliance for data integrity
- Excellent for complex queries and relationships
- JSON support for flexible fields
- Mature ecosystem with excellent tooling

Cons:
- Requires more upfront schema design
- Vertical scaling can be more complex
- May require more backend code for object mapping

Firebase:

Pros:

- Minimal backend code required
- Real-time updates built-in
- Integrated with other Google Cloud services
- Includes authentication and storage solutions

Cons:

- Less control over complex queries
- Potential vendor lock-in
- Could become costly at scale
- Limited complex join capabilities
- This structured comparison helps you weigh important factors for your specific use case rather than getting a generic recommendation.

---

## 3. Stepwise Chain of Thought Prompt Strategy

### When To Use It:
When you need more control over what how your AI should perform on complex tasks.
Example : With a single prompt, AI gave a massive refactoring plan that went completely off the rails by step three.
The stepwise approach lets you keep your hands on the steering wheel throughout the process, applying your domain knowledge as you go along with the proces.

### How It Works:
1. You instruct the AI to solve a problem by breaking it into distinct steps
2. The AI completes only one step, then stops and waits for your approval
3. You review the step and provide feedback or confirmation
4. Only after your confirmation does the AI proceed to the next step
5. This continues until the entire problem is solved

### Benefits:
- Gives you control over the pace and direction of the solution
- Allows you to review and course-correct at each stage
- Prevents the AI from making compounding errors
- Creates opportunities to refine requirements as you go
- Makes complex processes more manageable


### Example Use Case:
Instead of asking:

```
Refactor this messy JavaScript service file to improve its structure and readability
```

Use the stepwise chain of thought strategy:

```
Help me refactor the code in service.js.
Go one step at a time.
Do not move to the next step until I give the keyword ‘next’.
```

The AI might respond with:

**Step 1: Analyze the current code structure** Looking at your service.js file, I can see several issues that need addressing:

1. The file contains multiple unrelated functions that should be separated by concern
2. There’s significant code duplication in the error handling
3. Several functions are unnecessarily complex with too many responsibilities
4. Variable naming is inconsistent

Let me know if you agree with this assessment by typing “next” and I’ll proceed with the first refactoring step.

After you reply “next”, the AI would continue:

**Step 2: Separate concerns into logical modules** Let’s start by grouping related functions. I recommend splitting this file into three separate modules:

- userService.js — For user-related operations
- productService.js — For product-related operations
- utilService.js — For shared utility functions

Here’s how we would reorganize the functions: \[specific code examples for reorganization\]

Type “next” when you’re ready for me to show you how to refactor the error handling.

This approach ensures you maintain control and can guide the refactoring process at each stage.

---

## 4. Role Prompt Strategy

### When To Use It:
When preparing for a security audit and realized you don't have a security specialist to review your code.<BR>
By asking the AI to “think like a security engineer,” you can uncover several vulnerabilities that weren’t obvious to you as a full-stack dev.<BR>
Use it to get perspectives from roles that you don’t have on your team.<BR>

### How It Works:
1. You ask the AI to assume a specific professional role or expertise
2. You describe the context and questions you have for that role
3. The AI responds with the mindset, knowledge, and perspective of that specialist
4. You get advice that reflects that role’s priorities and expertise

### Benefits:
- Focuses responses toward specific domain expertise
- Highlights considerations particular to that role or discipline
- Provides specialized vocabulary and frameworks
- Can uncover blind spots in your thinking
- Helps simulate different stakeholder perspectives

### Example Use Case:
Instead of asking:

```
Review this authentication code for my web app
```

Use the role prompt strategy:

```
Act as a senior security engineer with 10 years of experience in web application security.
Review the following authentication code for my React application and
identify any security vulnerabilities, potential edge cases, or implementation flaws.
Be particularly attentive to common OWASP security risks.

function authenticateUser(email, password) {
  // Code to be reviewed
  const user = database.findUserByEmail(email);
  if (user && user.password === password) {
    const token = generateToken(user.id);
    return { success: true, token };
  }
  return { success: false, message: 'Invalid credentials' };
}

```

__(Read Footnote if your codefiles are multiple files)__

The AI, taking on the security engineer role, might respond with:

“As a security engineer, I’ve identified several critical vulnerabilities in your authentication implementation:

1. **Plain Text Password Comparison:** You’re storing and comparing passwords in plain text. This is a severe security risk (OWASP A02:2021). Passwords should always be hashed using a strong algorithm like bcrypt or Argon2.
2. **No Input Validation:** There’s no validation for the email or password inputs, leaving you vulnerable to injection attacks (OWASP A03:2021).
3. **Insufficient Error Handling:** Your error message doesn’t differentiate between a non-existent user and wrong password, which is good for security, but there’s no rate limiting to prevent brute force attacks.
4. **Token Generation:** Without seeing the implementation of `generateToken()`, I can't assess if it's secure, but ensure you're using sufficient entropy and including expiration.

Here’s a more secure implementation…”

By specifying the role, you get feedback that prioritizes security considerations that might be overlooked by a more general code review.


---

# Advanced Prompting: Combined Strategies
Once you have the basic patterns nailed down, you can try to Combine the Strategies.

## Role + Q&A Strategy
This combo is useful when dealing with areas outside your expertise.<BR>
Example: You are not familiar with Kubernetes, and when setting up Kubernetes for the first time, it can save you from several rookie mistakes.

```
Act as a DevOps engineer with expertise in Kubernetes.
I need help setting up a CI/CD pipeline for our microservices architecture.
Before providing a solution, please ask me questions about our current infrastructure, team capabilities,
and specific requirements to ensure your guidance is tailored to our situation.
```

## Stepwise + Pros and Cons Strategy
Get a "third eye" on technical decisions for complex projects.<BR>
Example : Microservices migration project, and it can help prevent from breaking up services in ways you might regret later. 
It forces careful consideration at each decision point.

```
I need to migrate our application from a monolithic architecture to microservices.
Let’s approach this one step at a time, and for each step,
I’d like you to present multiple approaches with their pros and cons.
First, help me identify which components should be separated into microservices.
Don’t proceed to the next step until I type ‘next’.
```

## Role + Stepwise Strategy
Use this when working in unfamiliar territory. 
Example : You are asked to optimize our database performance, an area where you are not an expert. It was like having a senior DBA pair-programming with you, but one who moved at my pace.

```
Act as a senior database architect.
I need to optimize our PostgreSQL database that’s experiencing performance issues with our e-commerce application.
Walk me through the optimization process step by step, explaining your reasoning at each stage.
Wait for my confirmation before moving to the next step.
```

## Q&A + Pros and Cons + Stepwise Strategy
Also known as the “big decision” pattern, it takes longer.<BR>
Useful for the most complex architectural decisions (especially high-stakes technical choices).

```
I’m designing a real-time data processing system for IoT devices.
First, please ask me clarifying questions about our requirements and constraints.
Then, present the pros and cons of different architectural approaches (Kafka vs. RabbitMQ, serverless vs. container-based, etc.).
Finally, once we’ve settled on an approach, guide me through the implementation step by step, waiting for my confirmation at each stage.
```

# Conculsion

The AI is still just a tool. Your experience, intuition, and project knowledge are what make these strategies effective. The AI suggests; you decide.

---

# Useful Tip:

Sometimes your codes will be more than 9 lines.<BR>
- You can choose to upload your code file (single file).
- Or in case of codes spread across multiple files, use [Repomix](https://github.com/yamadashy/repomix) to merge code files into 1 file for ease of upload.
- Repomix is a powerful tool that packs your entire repository into a single, AI-friendly file. Perfect for when you need to feed your codebase to Large Language Models (LLMs) or other AI tools like Claude, ChatGPT, DeepSeek, Perplexity, Gemini, Gemma, Llama, Grok, and more.

---

[Source / Credits](https://reykario.medium.com/4-must-know-ai-prompt-strategies-for-developers-0572e85a0730)
