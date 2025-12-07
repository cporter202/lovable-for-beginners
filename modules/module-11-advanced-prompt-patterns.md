# Module 11: Advanced Prompt Patterns

**Goal:** Master advanced techniques for complex applications

**Estimated Time:** 40-50 minutes

**Prerequisites:** Complete Modules 1-5 first

---

## 🎯 What You'll Learn in This Module

By the end of this module, you will:
- Understand advanced prompt patterns for complex flows
- Know how to create dynamic, data-driven content
- Learn conditional logic in prompts
- Understand how to handle loops and iterations
- Be able to build more sophisticated applications
- Know patterns for complex user interactions

---

## 📖 Lesson 1: Dynamic Content Generation

### What is Dynamic Content?

**Dynamic content** changes based on data, user input, or conditions. Instead of static pages, you create pages that adapt.

### Basic Dynamic Content

**Example:**
```
Create a blog post page that displays:
- Post title (from database)
- Post content (from database)
- Author name (from database)
- Publication date (from database)
- Related posts (based on category)
```

**What this does:** Creates a template that fills with different data for each post.

### Advanced Dynamic Patterns

#### Pattern 1: Conditional Display

**Example:**
```
On the product page, show different content based on product availability:
- If product is in stock: Show "Add to Cart" button and stock count
- If product is out of stock: Show "Notify Me" button and "Out of Stock" message
- If product is on sale: Show sale badge and discounted price
```

#### Pattern 2: Data-Driven Lists

**Example:**
```
Create a task list that:
- Shows all tasks from the database
- Displays different information based on task status:
  - Pending tasks: Show in yellow with "Complete" button
  - Completed tasks: Show in green with strikethrough
  - Overdue tasks: Show in red with warning icon
- Updates automatically when tasks change
```

#### Pattern 3: User-Specific Content

**Example:**
```
Create a dashboard that shows:
- Personalized greeting with user's name
- Content based on user's role:
  - Admin users: Show admin panel and all data
  - Regular users: Show only their own data
  - Guest users: Show limited preview
- Recommendations based on user's activity
```

**💡 Beginner Tip:** Start simple, then add conditions. Build the basic version first, then add the conditional logic.

---

## 📖 Lesson 2: Conditional Logic in Prompts

### What is Conditional Logic?

**Conditional logic** means "if this, then that" - showing different content or behavior based on conditions.

### Basic Conditional Patterns

#### Pattern 1: Simple If-Then

**Example:**
```
Create a user profile page that:
- If user is logged in: Show full profile with edit button
- If user is not logged in: Show limited preview with "Sign up to see more" message
```

#### Pattern 2: Multiple Conditions

**Example:**
```
Create a product card component that displays differently based on:
- Product availability (in stock, out of stock, pre-order)
- Product type (physical, digital, subscription)
- User's purchase history (new, previously purchased, in cart)
Show appropriate buttons and information for each combination
```

#### Pattern 3: Conditional Styling

**Example:**
```
Style the task list items based on priority:
- High priority tasks: Red background, bold text, urgent icon
- Medium priority tasks: Yellow background, normal text
- Low priority tasks: Gray background, lighter text
- Completed tasks: Green checkmark, strikethrough, grayed out
```

### Advanced Conditional Patterns

#### Pattern 4: Nested Conditions

**Example:**
```
Create a notification system that shows different messages based on:
- User type (admin, member, guest)
  - If admin: Show all notifications including system alerts
  - If member: Show user-specific notifications
  - If guest: Show only public announcements
- Notification type (message, alert, update)
  - Messages: Show sender and preview
  - Alerts: Show with warning icon
  - Updates: Show with info icon
- Read status (read, unread)
  - Unread: Bold and highlighted
  - Read: Normal styling
```

#### Pattern 5: Conditional Features

**Example:**
```
Add features to the dashboard based on subscription level:
- Free users: Basic features only
- Pro users: Add advanced analytics and export
- Enterprise users: Add team collaboration and API access
Show upgrade prompts for features locked to higher tiers
```

**💡 Beginner Tip:** Break complex conditions into smaller parts. Build one condition at a time, test it, then add the next.

---

## 📖 Lesson 3: Loops and Iterations

### What are Loops?

**Loops** repeat actions for multiple items. Like saying "do this for each item in the list."

### Basic Loop Patterns

#### Pattern 1: Display List Items

**Example:**
```
Create a blog listing page that:
- Fetches all blog posts from the database
- For each post, display:
  - Post title (as clickable link)
  - Featured image
  - Excerpt (first 150 characters)
  - Author name
  - Publication date
  - Read more button
- Show 10 posts per page with pagination
```

#### Pattern 2: Generate Multiple Components

**Example:**
```
Create a services page that displays:
- For each service in the database, create a service card showing:
  - Service name
  - Description
  - Price
  - "Learn More" button
- Arrange cards in a responsive grid (3 columns on desktop, 1 on mobile)
```

#### Pattern 3: Dynamic Forms

**Example:**
```
Create a dynamic survey form that:
- Loads questions from the database
- For each question, displays:
  - Question text
  - Appropriate input type (text, multiple choice, rating, etc.)
  - Required/optional indicator
- Validates and submits all answers together
```

### Advanced Loop Patterns

#### Pattern 4: Nested Loops

**Example:**
```
Create a category page that shows:
- For each category:
  - Category name and description
  - For each product in that category:
    - Product card with image, name, price
  - "View All" link for the category
- Organize categories in sections
```

#### Pattern 5: Conditional Loops

**Example:**
```
Create a task dashboard that:
- For each task category (Work, Personal, Shopping):
  - Show category header
  - For each task in that category:
    - If task is not completed: Show full task card
    - If task is completed: Show collapsed/minimized card
  - Show category statistics (total, completed, pending)
```

**💡 Beginner Tip:** Loops are powerful! Use them whenever you need to display multiple similar items.

---

## 📖 Lesson 4: Complex User Flows

### What are User Flows?

**User flows** are the paths users take through your app to complete tasks. Complex flows have multiple steps and decisions.

### Multi-Step Flow Patterns

#### Pattern 1: Wizard/Onboarding Flow

**Example:**
```
Create a multi-step onboarding wizard:
- Step 1: Welcome and account setup
- Step 2: Profile information (name, bio, preferences)
- Step 3: Choose interests/categories
- Step 4: Set preferences and notifications
- Step 5: Confirmation and completion
Each step should:
- Save progress (so users can go back)
- Show progress indicator
- Have "Next" and "Back" buttons
- Validate before proceeding
```

#### Pattern 2: Checkout Flow

**Example:**
```
Create a checkout process with steps:
- Step 1: Review cart items
- Step 2: Shipping information
- Step 3: Payment method
- Step 4: Order confirmation
- Each step validates before allowing next step
- Show progress: "Step 2 of 4"
- Allow going back to previous steps
- Save information as user progresses
```

#### Pattern 3: Approval Workflow

**Example:**
```
Create a content approval system:
- Author creates content → Status: "Draft"
- Author submits for review → Status: "Pending Review"
- Reviewer approves → Status: "Approved" → Published
- Reviewer rejects → Status: "Rejected" → Returned to author with comments
- Show different views based on status and user role
```

### State Management Patterns

#### Pattern 4: Form State Management

**Example:**
```
Create a complex form that:
- Saves progress automatically as user types
- Shows which fields are completed
- Validates fields in real-time
- Shows error messages immediately
- Allows saving as draft
- Prevents data loss if user navigates away
```

#### Pattern 5: Multi-Select with Dependencies

**Example:**
```
Create a product configuration form where:
- User selects product type → Shows relevant options
- User selects size → Updates available colors
- User selects color → Updates available materials
- Each selection updates what's available next
- Shows running total price
- Validates that all required selections are made
```

**💡 Beginner Tip:** Break complex flows into clear steps. Test each step before building the next.

---

## 📖 Lesson 5: Advanced Prompt Structures

### Pattern 1: Template-Based Generation

**Example:**
```
Create email templates for different scenarios:
- Welcome email (when user signs up)
- Password reset email
- Order confirmation email
- Newsletter email
Each template should:
- Use user's name dynamically
- Include relevant information
- Match brand styling
- Be responsive for email clients
```

### Pattern 2: Component Composition

**Example:**
```
Build a dashboard using reusable components:
- Header component (used on all pages)
- Stats card component (reused for different metrics)
- Chart component (used for different data visualizations)
- Action button component (consistent across app)
Each component should be flexible and reusable
```

### Pattern 3: Data Transformation

**Example:**
```
Create a data display that:
- Fetches raw data from API
- Transforms it: formats dates, calculates totals, groups by category
- Displays in user-friendly format:
  - Charts for numerical data
  - Tables for structured data
  - Cards for individual items
- Updates when data changes
```

### Pattern 4: Event-Driven Patterns

**Example:**
```
Create an interactive app where:
- User actions trigger updates:
  - Clicking "Like" updates like count immediately
  - Adding to cart updates cart icon badge
  - Submitting form shows success message
- Multiple components update based on same action
- Changes reflect immediately without page refresh
```

---

## 🛠️ Hands-On Practice

### Practice 1: Dynamic Product Display

**Challenge:** Create a product listing that shows different information based on product status.

**Requirements:**
- Display products from database
- Show "In Stock" badge for available products
- Show "Sale" badge for discounted products
- Show "New" badge for recently added products
- Different styling for each status
- Products can have multiple badges

**💡 Hint:** Use conditional logic in your prompt to handle different statuses.

### Practice 2: Multi-Step Form

**Challenge:** Create a registration form with 3 steps.

**Requirements:**
- Step 1: Basic info (name, email)
- Step 2: Preferences (interests, newsletter)
- Step 3: Confirmation
- Progress indicator
- Can go back to previous steps
- Validates each step

**💡 Hint:** Build one step at a time, then connect them.

### Practice 3: Conditional Dashboard

**Challenge:** Create a dashboard that changes based on user role.

**Requirements:**
- Admin users see: All users, system stats, admin tools
- Regular users see: Their own data, personal stats
- Guest users see: Limited preview, sign up prompt
- Same page, different content

**💡 Hint:** Use conditional logic to show/hide sections based on user role.

---

## ✅ Module 11 Checklist

Before moving to the next module, make sure you can:

- [ ] Create dynamic content that changes based on data
- [ ] Use conditional logic in prompts
- [ ] Create loops for displaying multiple items
- [ ] Build multi-step user flows
- [ ] Handle complex state management
- [ ] Use advanced prompt patterns effectively

---

## 🤔 Common Questions (FAQ)

### Q: How complex can prompts get?
**A:** Very complex! But start simple and build up. Break complex requests into smaller parts.

### Q: Should I use these patterns for simple projects?
**A:** Not always. Use simple prompts for simple projects. Use advanced patterns when you need the complexity.

### Q: What if my conditional logic doesn't work?
**A:** Break it down. Test each condition separately, then combine them.

### Q: Can I combine multiple patterns?
**A:** Yes! Advanced apps often use multiple patterns together.

---

## 🎯 What's Next?

Great work! You now understand advanced prompt patterns. These techniques help you build more sophisticated applications.

**Continue learning with:**
- Module 12: Performance and Optimization
- Module 13: Advanced API Integration
- Or go back to Module 9 to build your capstone project!

---

*Module 11 Complete! 🎉*

