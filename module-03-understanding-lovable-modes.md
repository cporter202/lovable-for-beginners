# Module 3: Understanding Lovable's Modes - How to Talk to AI

**Goal:** Master the different ways to interact with Lovable

**Estimated Time:** 25-30 minutes

---

## 🎯 What You'll Learn in This Module

By the end of this module, you will:
- Understand what Chat Mode is and when to use it
- Understand what Agent Mode is and when to use it
- Know the key differences between the two modes
- Be able to choose the right mode for different tasks
- Understand how credits work for each mode
- Know how to switch between modes

---

## 📖 Lesson 1: Introduction to Modes

### What Are Modes?

Think of **modes** as different ways to talk to Lovable, each designed for different purposes. It's like having two different tools - one for planning and one for building.

### The Two Main Modes

Lovable has two main modes:

1. **Chat Mode** - For talking, planning, and understanding
2. **Agent Mode** - For building and making changes automatically

**💡 Beginner Tip:** Don't worry about understanding everything right away. We'll explain each mode in detail, and you'll get the hang of it quickly!

---

## 📖 Lesson 2: Chat Mode - Your Development Partner

### What is Chat Mode?

**Chat Mode** is like having a conversation with a helpful developer friend. You can ask questions, get advice, plan your project, and understand how things work - but Chat Mode **doesn't make changes to your code automatically**.

### When to Use Chat Mode

Use Chat Mode when you want to:

✅ **Ask questions** - "How should I organize my app?"  
✅ **Get advice** - "What's the best way to add user authentication?"  
✅ **Plan features** - "How should I structure my database?"  
✅ **Debug problems** - "Why isn't my button working?"  
✅ **Understand code** - "What does this code do?"  
✅ **Get suggestions** - "What features should I add next?"

### How Chat Mode Works

#### Step 1: Activate Chat Mode

1. Look at the input box where you type messages
2. You'll see a button or toggle that says **"Chat"** or shows a chat icon
3. Click it to activate Chat Mode
4. The button will highlight or change to show Chat Mode is active

**Visual indicator:** You might see "Chat" highlighted or a different color when Chat Mode is active.

#### Step 2: Ask Your Question

Type your question or request, just like having a conversation:

**Examples:**

```
How should I organize my portfolio website?
```

```
What's the best way to add a contact form?
```

```
Can you explain how authentication works?
```

```
Help me plan the structure for my e-commerce site
```

#### Step 3: Get Helpful Responses

Chat Mode will:
- Answer your questions in detail
- Provide step-by-step guidance
- Explain concepts clearly
- Suggest best practices
- Help you think through problems

#### Step 4: The "Implement the Plan" Button

After Chat Mode helps you plan, you might see a button that says **"Implement the plan"**. 

**What this does:**
- Chat Mode switches to Agent Mode
- Agent Mode then builds what you discussed
- It's like saying "Okay, now actually build this!"

**Example Flow:**

1. **You (Chat Mode):** "How should I add a navigation menu?"
2. **Chat Mode:** Explains the best approach and asks clarifying questions
3. **You:** Answer the questions
4. **Chat Mode:** Provides a detailed plan
5. **You:** Click "Implement the plan"
6. **Agent Mode:** Actually adds the navigation menu to your project

### Chat Mode Pricing

- **Cost:** 1 credit per message
- **What this means:** Each question or message you send costs 1 credit
- **Is it worth it?** Yes! Getting help and planning saves time and prevents mistakes

**📊 For complete pricing information:** See the [Pricing and Plans Guide](supplement-pricing-and-plans.md) for details on credits, plans, and how to monitor usage.

**💡 Beginner Tip:** Use Chat Mode liberally when you're learning. It's like having a tutor who never gets tired of your questions!

---

## 📖 Lesson 3: Agent Mode - The Autonomous Builder

### What is Agent Mode?

**Agent Mode** is like having a developer who works for you. You give instructions, and Agent Mode **automatically makes changes to your code** to build what you want.

### When to Use Agent Mode

Use Agent Mode when you want to:

✅ **Build features** - "Add a login page"  
✅ **Make changes** - "Change the colors to blue"  
✅ **Fix bugs** - "Fix the button that's not working"  
✅ **Add functionality** - "Add a search feature"  
✅ **Create new pages** - "Create an about page"  
✅ **Implement complex features** - "Add user authentication"

### How Agent Mode Works

#### Step 1: Activate Agent Mode

1. Look at the input box where you type messages
2. You'll see a button or toggle for **"Agent"** or an agent icon
3. Click it to activate Agent Mode
4. The button will highlight or change to show Agent Mode is active

**Visual indicator:** You might see "Agent" highlighted or a different color when Agent Mode is active.

#### Step 2: Give Your Instructions

Type what you want built, clearly and specifically:

**Examples:**

```
Add a navigation menu at the top with links to Home, About, and Contact
```

```
Create a contact form with fields for name, email, and message
```

```
Change the background color to dark blue and the text to white
```

```
Add a footer with social media icons
```

#### Step 3: Watch Agent Mode Work

Agent Mode will:
- Understand your request
- Explore your codebase to understand the structure
- Make the necessary changes
- Test to make sure it works
- Show you what was changed

**What you'll see:**
- A loading indicator while Agent Mode works
- Changes appearing in your project
- A summary of what was done

#### Step 4: Review the Changes

After Agent Mode finishes:
- **Check the preview** - See if it looks right
- **Test functionality** - Make sure it works as expected
- **Ask for adjustments** - If something isn't quite right, ask for changes

---

## 📖 Lesson 3.5: Agent Mode for Complex Operations

### Understanding Complex Operations

**Complex operations** are multi-step tasks that require Agent Mode to:
- Work on multiple files
- Make coordinated changes
- Build interconnected features
- Handle dependencies between features

### How Agent Mode Handles Complex Tasks

When you give Agent Mode a complex task, it:

1. **Analyzes the request** - Understands what needs to be built
2. **Explores your codebase** - Reads relevant files to understand structure
3. **Creates a plan** - Decides the order of operations
4. **Executes step by step** - Makes changes systematically
5. **Tests as it goes** - Ensures each step works before moving on
6. **Reports progress** - Shows you what it's doing

**What you'll see during complex operations:**
- Progress updates
- Files being modified
- Steps being completed
- Any issues encountered

### Multi-Step Planning Examples

#### Example 1: Building Authentication System

**Single Complex Request:**
```
Add complete user authentication: sign up page, login page, logout functionality, and protect the dashboard so only logged-in users can access it.
```

**What Agent Mode does:**
1. Creates sign up page with form
2. Creates login page with form
3. Sets up authentication backend
4. Adds logout button
5. Protects dashboard route
6. Updates navigation to show different items for logged-in users
7. Tests the flow

**Better Approach - Step by Step:**

**Step 1:**
```
Create a sign up page with email and password fields, and connect it to authentication
```

**Step 2:**
```
Create a login page that matches the sign up page design
```

**Step 3:**
```
Add logout functionality and update the navigation to show user name and logout button when logged in
```

**Step 4:**
```
Protect the dashboard page so only logged-in users can access it. Redirect others to login.
```

**Why step-by-step is better:**
- ✅ You can review each step
- ✅ Easier to catch issues early
- ✅ More control over the process
- ✅ Can adjust direction if needed

#### Example 2: Building E-commerce Features

**Complex Request:**
```
Add e-commerce functionality: product listing page, product detail page, shopping cart, and checkout with Stripe payment integration.
```

**What Agent Mode does:**
1. Creates product database structure
2. Builds product listing page
3. Creates product detail pages
4. Implements shopping cart
5. Connects Stripe
6. Builds checkout flow
7. Tests payment processing

**Better Approach - Incremental:**

**Step 1:**
```
Create a product listing page that displays products from a database
```

**Step 2:**
```
Add product detail pages that show full product information
```

**Step 3:**
```
Add a shopping cart that stores selected products
```

**Step 4:**
```
Integrate Stripe and create a checkout page for payment processing
```

#### Example 3: Refining UI After Building Features

**Workflow:**
1. **Build the feature** (Agent Mode)
2. **Review the result** (You)
3. **Refine the UI** (Agent Mode)
4. **Add polish** (Agent Mode)

**Example:**

**Step 1 - Build:**
```
Add user authentication with sign up and login pages
```

**Step 2 - Review:**
You check the pages and notice they're functional but need design improvements.

**Step 3 - Refine:**
```
Improve the design of the sign up and login pages: add better spacing, improve colors, make the forms more visually appealing, and add error message styling
```

**Step 4 - Polish:**
```
Add smooth animations to the authentication forms and improve the user experience with loading states
```

### Best Practices for Writing Instructions to Agent Mode

#### 1. Break Tasks into Smaller Steps

**❌ Too Complex:**
```
Build a complete blog with posts, categories, tags, comments, author profiles, search, and admin panel
```

**✅ Better - Broken Down:**
```
Step 1: Create a blog post database and listing page
Step 2: Add individual post pages
Step 3: Add categories and filtering
Step 4: Add comments functionality
Step 5: Create author profile pages
Step 6: Add search feature
Step 7: Build admin panel for managing posts
```

#### 2. Be Specific About Requirements

**❌ Vague:**
```
Add a form
```

**✅ Specific:**
```
Create a contact form with:
- Name field (required, text input)
- Email field (required, email validation)
- Message field (required, textarea)
- Submit button
- Success message after submission
- Error handling for invalid inputs
Make it match the design of the rest of the site
```

#### 3. Provide Context

**❌ No Context:**
```
Add authentication
```

**✅ With Context:**
```
Add user authentication for my task manager app. Users need to sign up and login to access their tasks. The authentication should work with the existing database structure and match the app's blue and white color scheme.
```

#### 4. Review Intermediate Changes

**Best Practice:**
- Build one feature
- Test it
- Review it
- Then build the next feature

**Example:**
```
1. "Add a navigation menu" → Test → Review
2. "Add a hero section" → Test → Review  
3. "Add a footer" → Test → Review
```

#### 5. Use Clear, Action-Oriented Language

**❌ Unclear:**
```
Maybe make the page better
```

**✅ Clear:**
```
Improve the homepage by:
- Increasing spacing between sections
- Making headings larger and bolder
- Adding hover effects to buttons
- Improving color contrast for readability
```

#### 6. Specify What NOT to Change

**Example:**
```
Add a new "Services" page, but don't change the existing navigation or homepage design
```

#### 7. Ask for Confirmation on Major Changes

**Example:**
```
I want to restructure the entire navigation. Before you do it, can you show me what the new structure will look like?
```

### How to Cancel or Roll Back Agent Operations

#### Canceling an Operation

**If Agent Mode is still working:**

1. **Look for a "Cancel" or "Stop" button** - Usually near the progress indicator
2. **Click it** - Agent Mode will stop what it's doing
3. **Review what was done** - Check what changes were made before canceling
4. **Decide next steps** - Continue, revert, or try a different approach

**What happens:**
- Agent Mode stops immediately
- Changes made so far remain (unless you revert)
- You can start a new operation

#### Rolling Back Changes

**If Agent Mode completed but you don't like the result:**

**Option 1: Use History**
1. Go to **History** or **Version History**
2. Find the version before Agent Mode made changes
3. Click **"Revert"** or **"Restore"**
4. Your project goes back to that version

**Option 2: Ask to Undo**
```
Revert the last change Agent Mode made
```

or

```
Undo the changes you just made to the navigation
```

**Option 3: Edit Your Message**
1. Find the message that triggered the change
2. Edit or delete it
3. Lovable will adjust accordingly

**Option 4: Ask for the Opposite**
```
Remove the feature I just added
```

or

```
Change it back to how it was before
```

### Monitoring Agent Mode Progress

**What to watch for:**

1. **Progress indicators** - Shows what step Agent Mode is on
2. **File changes** - See which files are being modified
3. **Status messages** - Read what Agent Mode is doing
4. **Error messages** - If something goes wrong, you'll see it

**If something seems wrong:**
- **Cancel the operation** - Stop it before more changes
- **Check error messages** - Read what went wrong
- **Ask Chat Mode** - "What went wrong with that operation?"
- **Try a different approach** - Break it into smaller steps

### Working with Agent Mode on Large Projects

**For complex, multi-feature projects:**

1. **Plan in Chat Mode first**
   ```
   I want to build an e-commerce site. Can you help me plan the features and order?
   ```

2. **Build incrementally**
   - One feature at a time
   - Test each feature
   - Review before moving on

3. **Use version control**
   - Save good versions in History
   - Mark milestones
   - Easy to revert if needed

4. **Review regularly**
   - Check what Agent Mode built
   - Test functionality
   - Request adjustments before building more

5. **Communicate clearly**
   - Be specific about what you want
   - Provide context
   - Specify constraints

### Agent Mode Pricing

- **Cost:** Usage-based (varies by complexity)
- **What this means:** Simple tasks might cost less than 1 credit, complex tasks might cost more
- **Why it varies:** More complex tasks require more AI processing

**📊 For complete pricing information:** See the [Pricing and Plans Guide](supplement-pricing-and-plans.md) for details on credits, plans, and how to monitor usage.

**💡 Beginner Tip:** Don't worry about credits too much when starting. Focus on learning - you'll get a feel for what costs what as you use Lovable more. Most simple tasks cost very little!

---

## 📖 Lesson 4: Key Differences Between Chat and Agent Mode

### Quick Comparison

| Feature | Chat Mode | Agent Mode |
|---------|-----------|------------|
| **Makes changes?** | ❌ No - just talks | ✅ Yes - builds automatically |
| **Best for** | Questions, planning | Building, implementing |
| **Cost** | 1 credit per message | Varies by complexity |
| **Speed** | Instant responses | Takes time to build |
| **Use when** | You need help/advice | You want something built |

### Real-World Examples

#### Example 1: Adding a Contact Form

**Using Chat Mode:**
```
You: "How should I add a contact form?"
Chat Mode: Explains the best approach, asks about fields, suggests design
You: Get advice and understand the process
Result: You understand how to do it, but nothing is built yet
```

**Using Agent Mode:**
```
You: "Add a contact form with name, email, and message fields"
Agent Mode: Builds the form automatically
Result: Contact form is added to your project
```

#### Example 2: Fixing a Bug

**Using Chat Mode:**
```
You: "My button isn't working. Why?"
Chat Mode: Investigates, explains the problem, suggests solutions
You: Understand what's wrong
Result: You know how to fix it
```

**Using Agent Mode:**
```
You: "Fix the button that's not working"
Agent Mode: Finds the problem, fixes it automatically
Result: Button is fixed
```

### When to Use Which Mode

**Use Chat Mode when:**
- You're not sure what you want
- You need to understand something
- You want to plan before building
- You're learning and asking questions
- You want advice on best practices

**Use Agent Mode when:**
- You know exactly what you want
- You're ready to build something
- You want changes made automatically
- You're implementing a feature
- You're fixing something specific

**💡 Beginner Tip:** A common workflow is: Use Chat Mode to plan, then use Agent Mode (or click "Implement the plan") to build it!

---

## 📖 Lesson 5: Switching Between Modes

### How to Switch

Switching between modes is easy:

1. **Look at the input box** - You'll see buttons or toggles for Chat and Agent
2. **Click the mode you want** - Click "Chat" for Chat Mode, "Agent" for Agent Mode
3. **The active mode will be highlighted** - You'll see which mode is currently selected

### When to Switch

**Switch to Chat Mode when:**
- You're stuck and need help
- You want to understand something
- You need to plan before building
- You want advice

**Switch to Agent Mode when:**
- You're ready to build something
- You have clear instructions
- You want changes made
- You're implementing a feature

### Using Both Modes Together

A great workflow is to use both modes:

1. **Start in Chat Mode** - Ask questions and plan
2. **Get advice** - Understand what you need to do
3. **Switch to Agent Mode** - Actually build it
4. **Go back to Chat Mode** - If you need to understand or adjust

**Example Workflow:**

```
1. Chat Mode: "How should I add user authentication?"
2. Chat Mode: Explains the process, asks questions
3. You: Answer questions
4. Chat Mode: Provides a plan
5. Click "Implement the plan" OR switch to Agent Mode
6. Agent Mode: Builds the authentication system
7. Chat Mode: "Can you explain how this works?"
8. Chat Mode: Explains the authentication system
```

---

## 🛠️ Hands-On Practice

Let's practice using both modes!

### Practice 1: Using Chat Mode

**Task:** Get help planning a feature

1. **Activate Chat Mode** (click the Chat button)
2. **Ask this question:**
   ```
   I want to create a blog. How should I structure it? What pages do I need?
   ```
3. **Read the response** - Chat Mode will explain and ask questions
4. **Answer any questions** it asks
5. **Review the plan** it provides

**What you learned:** Chat Mode helps you think through and plan your project.

### Practice 2: Using Agent Mode

**Task:** Build a simple feature

1. **Activate Agent Mode** (click the Agent button)
2. **Give this instruction:**
   ```
   Add a header to my page with a logo on the left and navigation menu on the right
   ```
3. **Watch Agent Mode work** - It will build the header
4. **Check the result** - See if it looks good
5. **Ask for adjustments if needed:**
   ```
   Make the header background darker and the text white
   ```

**What you learned:** Agent Mode automatically builds what you ask for.

### Practice 3: Using Both Modes Together

**Task:** Plan and build a feature

1. **Start in Chat Mode:**
   ```
   I want to add a testimonials section to my website. What's the best way to do this?
   ```
2. **Get advice** from Chat Mode
3. **Click "Implement the plan"** or switch to Agent Mode
4. **Watch it get built**
5. **Go back to Chat Mode** if you need to understand something:
   ```
   How does this testimonials section work?
   ```

**What you learned:** Using both modes together gives you the best of both worlds - understanding and building.

### Practice 4: Complex Multi-Step Operation

**Task:** Build a feature incrementally using best practices

**Step 1 - Plan in Chat Mode:**
1. **Ask Chat Mode:**
   ```
   I want to add a contact section with a form and a map. Can you help me plan how to build this step by step?
   ```
2. **Get a plan** from Chat Mode
3. **Review the plan** - Understand the steps

**Step 2 - Build Step by Step:**

**Step 2a: Build the form first**
1. **Switch to Agent Mode**
2. **Give this instruction:**
   ```
   Create a contact form with name, email, phone, and message fields. Add form validation and a submit button.
   ```
3. **Wait for it to complete**
4. **Test the form** - Make sure it works
5. **Review** - Does it look good?

**Step 2b: Add the map**
1. **Still in Agent Mode**
2. **Give this instruction:**
   ```
   Add a map section below the contact form showing our business location
   ```
3. **Wait for it to complete**
4. **Test** - Check if the map displays
5. **Review** - Does it look good?

**Step 2c: Refine the design**
1. **Still in Agent Mode**
2. **Give this instruction:**
   ```
   Improve the contact section design: make the form and map side by side on desktop, stack them on mobile, and improve spacing and colors
   ```
3. **Wait for it to complete**
4. **Test on different screen sizes**
5. **Review** - Does it look good?

**What you learned:** Breaking complex features into steps gives you more control and better results.

### Practice 5: Canceling and Rolling Back

**Task:** Practice canceling and reverting operations

**Part A: Cancel an Operation (if needed)**
1. **Start Agent Mode** on a simple task
2. **If you change your mind** while it's working:
   - Look for "Cancel" or "Stop" button
   - Click it
   - Operation stops

**Part B: Roll Back Changes**
1. **Make a change** with Agent Mode:
   ```
   Change all the text colors to red
   ```
2. **Review the change** - See if you like it
3. **If you don't like it, revert:**
   - Go to **History**
   - Find the version before the change
   - Click **"Revert"**
   - Or ask: "Revert the last change"

**What you learned:** You can always undo changes, so don't be afraid to experiment!

---

## 🎯 Module 3 Challenges

**Master Chat and Agent Mode with these challenges!**

### Challenge 1: Plan Then Build (Beginner)

**Your Task:** Use Chat Mode to plan, then Agent Mode to build a feature.

**Feature:** Add a newsletter signup section to your homepage

**Steps:**
1. Use Chat Mode to plan the feature
2. Get advice on design and functionality
3. Click "Implement the plan" or switch to Agent Mode
4. Review what was built
5. Use Chat Mode to understand how it works

**💡 Hints:**
- Start with Chat Mode questions
- Let it ask you clarifying questions
- Review the plan before implementing
- Test after building

**Check your solution:** See [Challenge Solutions](supplement-challenge-solutions.md#module-3-challenge-1)

---

### Challenge 2: Complex Multi-Step Build (Intermediate)

**Your Task:** Build a complete feature using Agent Mode, breaking it into steps.

**Feature:** User profile system with avatar upload

**Requirements:**
- Build step 1: Create profile page
- Test and review
- Build step 2: Add avatar upload
- Test and review
- Build step 3: Add profile editing
- Test and review

**💡 Hints:**
- Don't build everything at once
- Test after each step
- Ask for adjustments if needed
- Use clear, specific instructions

**Check your solution:** See [Challenge Solutions](supplement-challenge-solutions.md#module-3-challenge-2)

---

### Challenge 3: Debug and Fix Workflow (Advanced)

**Your Task:** Practice the complete workflow of debugging and fixing.

**Scenario:** Your contact form isn't working properly

**Steps:**
1. Use Chat Mode to investigate the problem
2. Get explanation of what's wrong
3. Use Agent Mode to fix it
4. Test the fix
5. If needed, revert and try again

**💡 Hints:**
- Chat Mode for understanding
- Agent Mode for fixing
- Test thoroughly
- Use History if needed

**Check your solution:** See [Challenge Solutions](supplement-challenge-solutions.md#module-3-challenge-3)

---

**💡 Pro Tip:** These challenges help you practice the workflow you'll use in real projects!

---

## ✅ Module 3 Checklist

Before moving to Module 4, make sure you can:

- [ ] Explain the difference between Chat Mode and Agent Mode
- [ ] Know when to use Chat Mode
- [ ] Know when to use Agent Mode
- [ ] Successfully switch between modes
- [ ] Use Chat Mode to get help and plan
- [ ] Use Agent Mode to build features
- [ ] Understand the "Implement the plan" button
- [ ] Use both modes together effectively
- [ ] Break complex tasks into smaller steps
- [ ] Write clear, specific instructions for Agent Mode
- [ ] Cancel an Agent Mode operation if needed
- [ ] Roll back changes using History
- [ ] Review intermediate changes before building more

---

## 🤔 Common Questions (FAQ)

### Q: Which mode should I use most?
**A:** It depends! Use Chat Mode when learning and planning, Agent Mode when building. Many people use both throughout a project.

### Q: Can I use Chat Mode to build things?
**A:** Chat Mode doesn't build automatically, but it can help you plan, and then you can click "Implement the plan" to have Agent Mode build it.

### Q: What if Agent Mode doesn't build what I want?
**A:** That's okay! Ask for adjustments. You can say "That's not quite right, can you change it to..." and Agent Mode will fix it.

### Q: Do I need to switch modes manually?
**A:** Usually yes, but if you click "Implement the plan" in Chat Mode, it switches to Agent Mode automatically.

### Q: Can I use both modes in the same conversation?
**A:** Yes! You can switch back and forth as needed. That's actually a great way to work.

### Q: How do I know which mode I'm in?
**A:** Look at the mode buttons - the active one will be highlighted or shown differently.

### Q: How do I handle complex, multi-step features?
**A:** Break them into smaller steps! Build one feature at a time, test it, then build the next. This gives you more control and better results.

### Q: Can I cancel Agent Mode if it's doing something wrong?
**A:** Yes! Look for a "Cancel" or "Stop" button while Agent Mode is working. Click it to stop the operation immediately.

### Q: What if Agent Mode builds something I don't like?
**A:** You can roll it back! Go to History and revert to a previous version, or ask Agent Mode to undo the change.

### Q: Should I build everything at once or step by step?
**A:** Step by step is usually better! Build one feature, test it, review it, then build the next. This prevents issues and gives you more control.

### Q: How do I know if my instructions to Agent Mode are clear enough?
**A:** If Agent Mode builds what you want with minimal adjustments needed, your instructions were clear! If not, try being more specific or breaking it into smaller steps.

### Q: What if Agent Mode seems stuck or is taking too long?
**A:** Complex tasks take time. Check the progress indicators. If it's truly stuck, you can cancel and try breaking the task into smaller steps.

---

## 🎯 What's Next?

Fantastic! You now understand how to communicate with Lovable using both Chat Mode and Agent Mode. You can:
- Get help and advice with Chat Mode
- Build features automatically with Agent Mode
- Switch between modes as needed
- Use both modes together effectively

**Ready for Module 4?** In the next module, we'll learn how to edit and refine your projects - making changes, adding features, and improving your apps!

---

## 💡 Pro Tips for Beginners

1. **Start with Chat Mode** - When learning, use Chat Mode to understand things before building

2. **Don't be afraid to ask questions** - Chat Mode is there to help! Ask as many questions as you need

3. **Be specific with Agent Mode** - The clearer your instructions, the better the results

4. **Use "Implement the plan"** - It's a great way to go from planning to building seamlessly

5. **Switch modes freely** - Don't feel locked into one mode. Switch as needed!

6. **Learn from both** - Chat Mode teaches you, Agent Mode shows you how it's done

7. **Break complex tasks into steps** - Build incrementally for better control and results

8. **Review as you go** - Test each feature before building the next one

9. **Don't fear mistakes** - You can always cancel or roll back changes

10. **Plan before building** - Use Chat Mode to plan complex features, then build step by step

---

*Module 3 Complete! 🎉*

