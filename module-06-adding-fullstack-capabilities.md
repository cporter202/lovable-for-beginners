# Module 6: Adding Full-Stack Capabilities

**Goal:** Add powerful backend features to your applications

**Estimated Time:** 45-60 minutes

---

## 🎯 What You'll Learn in This Module

By the end of this module, you will:
- Understand what "full-stack" means
- Know how to use Lovable Cloud for backend features
- Understand how to use Connectors (Supabase, Stripe, etc.)
- Learn about MCP Servers for context
- Know how to integrate any API
- Be able to add authentication to your apps
- Understand how to add databases and storage
- Follow security best practices
- Store API keys securely
- Understand public vs. private API keys
- Build a complete payment integration project

---

## 📖 Lesson 1: Understanding Full-Stack

### What Does "Full-Stack" Mean?

**Full-stack** means your application has both:
- **Frontend** - What users see and interact with (the website/app)
- **Backend** - What happens behind the scenes (data storage, authentication, etc.)

### Simple Analogy

Think of a restaurant:
- **Frontend** = The dining room (what customers see)
- **Backend** = The kitchen (where the work happens)

Both are needed for a complete restaurant!

### What Backend Features Do You Need?

Common backend needs:
- **User accounts** - Sign up, login, logout
- **Data storage** - Save information (user data, posts, products, etc.)
- **Authentication** - Verify who users are
- **Payments** - Process transactions
- **Email** - Send notifications
- **File storage** - Store images, documents, etc.

**💡 Beginner Tip:** Don't worry if this sounds complex! Lovable makes it much easier than traditional coding.

---

## 📖 Lesson 2: Lovable Cloud - Built-in Backend

### What is Lovable Cloud?

**Lovable Cloud** is Lovable's built-in backend service. It provides everything you need for most applications without setting up separate services.

### What Lovable Cloud Provides

- ✅ **Authentication** - User sign up, login, logout
- ✅ **Database** - Store and retrieve data
- ✅ **File Storage** - Store images and files
- ✅ **API** - Connect your frontend to backend
- ✅ **Hosting** - Deploy your app

### When to Use Lovable Cloud

Use Lovable Cloud when:
- You need user accounts
- You need to store data
- You need file uploads
- You want everything in one place
- You're building a standard web app

### How to Enable Lovable Cloud

#### Step 1: Check if Cloud is Available

1. In your project, look for **"Cloud"** or **"Backend"** in settings
2. Or simply ask Lovable:
   ```
   Enable Lovable Cloud for this project
   ```

#### Step 2: Lovable Sets It Up

Lovable will:
- Create the backend infrastructure
- Set up the database
- Configure authentication
- Connect everything together

#### Step 3: Start Using It

Once enabled, you can ask for features:

```
Add user authentication - sign up, login, and logout
```

```
Create a database to store blog posts
```

```
Add file upload so users can upload profile pictures
```

**💡 Beginner Tip:** Lovable Cloud is the easiest way to add backend features. Start here!

---

## 📖 Lesson 3: Connectors - Add External Services

### What are Connectors?

**Connectors** are like plugins that connect your app to external services. They add powerful capabilities without you having to build them yourself.

### Popular Connectors

#### 1. Supabase - Authentication & Database

**What it does:**
- User authentication (sign up, login)
- Database for storing data
- Real-time updates
- File storage

**When to use:**
- You need a powerful database
- You want real-time features
- You need advanced authentication

**How to add:**
```
Connect Supabase to this project for authentication and database
```

#### 2. Stripe - Payments

**What it does:**
- Process payments
- Handle subscriptions
- Manage customers
- Process refunds

**When to use:**
- You're selling products
- You need subscriptions
- You're accepting payments

**How to add:**
```
Add Stripe payment processing to this project
```

#### 3. Shopify - E-commerce

**What it does:**
- Manage products
- Handle orders
- Process payments
- Manage inventory

**When to use:**
- Building an online store
- Selling products
- Need e-commerce features

**How to add:**
```
Connect Shopify for e-commerce functionality
```

#### 4. Resend - Email

**What it does:**
- Send emails
- Email notifications
- Transactional emails
- Marketing emails

**When to use:**
- Sending confirmation emails
- User notifications
- Contact form submissions
- Password resets

**How to add:**
```
Add Resend for email capabilities
```

### How Connectors Work

1. **Configure once** - Set up the connector in your workspace settings
2. **Use anywhere** - Use it in any project
3. **Lovable handles the connection** - You just ask for features
4. **Secure** - Credentials are stored safely

### Setting Up a Connector

#### Step 1: Get API Keys

Most connectors require API keys (like passwords for services):
1. Sign up for the service (Supabase, Stripe, etc.)
2. Get your API keys from their dashboard
3. Keep them safe (like passwords)

#### Step 2: Add to Lovable

1. Go to **Settings** → **Integrations** → **Connectors**
2. Click **"Add Connector"**
3. Select the service (Supabase, Stripe, etc.)
4. Enter your API keys
5. Save

#### Step 3: Use in Your Project

Once configured, just ask:

```
Add Stripe checkout to this product page
```

```
Use Supabase for user authentication
```

### Real Examples: Connecting Services

#### Example 1: Connecting Supabase

**Step 1: Get Supabase Credentials**
1. Sign up at [supabase.com](https://supabase.com)
2. Create a new project
3. Go to **Settings** → **API**
4. Copy your:
   - **Project URL** (e.g., `https://yourproject.supabase.co`)
   - **Anon/Public Key** (safe to use in frontend)
   - **Service Role Key** (keep secret - for backend only)

**Step 2: Add to Lovable**
1. Go to **Settings** → **Integrations** → **Connectors**
2. Click **"Add Connector"**
3. Select **"Supabase"**
4. Enter your Project URL and API keys
5. Save

**Step 3: Use Supabase in Your Project**

**For Authentication:**
```
Use Supabase for user authentication. Create sign up and login pages that connect to Supabase Auth.
```

**For Database:**
```
Set up Supabase database for storing blog posts. Create a table called 'posts' with fields: id, title, content, author_id, created_at.
```

**For Storage:**
```
Use Supabase Storage for uploading user profile pictures. Add an upload component to the profile page.
```

#### Example 2: Connecting Stripe

**Step 1: Get Stripe Keys**
1. Sign up at [stripe.com](https://stripe.com)
2. Go to **Developers** → **API keys**
3. Copy your:
   - **Publishable Key** (starts with `pk_` - safe for frontend)
   - **Secret Key** (starts with `sk_` - keep secret!)

**⚠️ IMPORTANT:** Never share your Secret Key! It's like a password.

**Step 2: Add to Lovable**
1. Go to **Settings** → **Integrations** → **Connectors**
2. Click **"Add Connector"**
3. Select **"Stripe"**
4. Enter your **Publishable Key** and **Secret Key**
5. Save

**Step 3: Use Stripe in Your Project**

**For One-Time Payments:**
```
Add Stripe payment to this product page. When user clicks "Buy Now", show Stripe checkout for $29.99.
```

**For Subscriptions:**
```
Add Stripe subscription to this page. Create a monthly subscription plan for $9.99/month with Stripe Checkout.
```

**For Payment Forms:**
```
Create a payment form using Stripe Elements. Include card number, expiry, and CVC fields. Process payment when form is submitted.
```

**💡 Beginner Tip:** Start with Lovable Cloud. Add connectors only when you need specific features they provide.

---

## 📖 Lesson 4: MCP Servers - Provide Context

### What are MCP Servers?

**MCP Servers** (Model Context Protocol) give Lovable access to your existing tools and data. They help Lovable understand your context better.

### What MCP Servers Do

MCP Servers:
- Connect to your existing tools (Linear, Notion, etc.)
- Provide context during app creation
- Help Lovable understand your workflows
- Are used only while building (not in the final app)

### Popular MCP Servers

#### Linear - Project Management

**What it does:**
- Imports issues and specs
- Understands your project requirements
- Builds features based on your tickets

**When to use:**
- You use Linear for project management
- You want to build from your tickets
- You have detailed specs in Linear

#### Notion - Documentation

**What it does:**
- Reads your Notion pages
- Uses your documentation as context
- Builds based on your notes

**When to use:**
- You document in Notion
- You want to build from your docs
- You have requirements in Notion

#### Atlassian (Jira/Confluence)

**What it does:**
- Accesses Jira tickets
- Reads Confluence documentation
- Builds from your specs

**When to use:**
- Your team uses Atlassian tools
- You have specs in Jira/Confluence
- You want to build from tickets

### How MCP Servers Work

1. **Configure the server** - Connect it to your tool
2. **Lovable uses it while building** - Provides context
3. **Not included in final app** - Only used during development
4. **Helps build better apps** - Lovable understands your needs

**💡 Beginner Tip:** MCP Servers are advanced. You can skip them for now and add them later if needed.

---

## 📖 Lesson 5: Integrating Any API

### What is an API?

**API** (Application Programming Interface) is how different services talk to each other. Think of it like a menu at a restaurant - it tells you what you can order.

### Why Integrate APIs?

APIs let you:
- Use data from other services
- Add features you didn't build
- Connect to external tools
- Extend your app's capabilities

### Types of APIs

#### Public APIs (No Authentication)

These don't require passwords/keys:

**Examples:**
- Weather data
- Public information
- Free services

**How to use:**
```
Integrate the weather API: https://api.weather.com/forecast
```

Lovable detects no authentication needed and adds it directly!

#### Private APIs (Require Authentication)

These need API keys (like passwords):

**Examples:**
- Payment processing
- User data
- Private services

**How to use:**
1. **Ask Lovable to integrate:**
   ```
   Integrate the OpenWeatherMap API for weather data.
   Base URL: https://api.openweathermap.org/data/2.5
   Auth: API key passed as appid parameter
   ```
2. **Enable Lovable Cloud** (if not already enabled)
3. **Add your API key:**
   - Go to **Cloud** → **Secrets**
   - Add your API key
   - Save it securely
4. **Lovable creates the integration** - Uses Edge Functions to keep keys safe

### Understanding Public vs. Private API Keys

**Public API Keys:**
- ✅ Safe to use in frontend code
- ✅ Can be visible in browser
- ✅ Limited permissions
- ✅ Examples: Stripe Publishable Key (starts with `pk_`), Supabase Anon Key
- ⚠️ Still should be kept reasonably secure

**Private/Secret API Keys:**
- ❌ **NEVER** expose in frontend code
- ❌ **NEVER** put in prompts or code
- ❌ **MUST** be stored in secrets manager
- ✅ Full access to account
- ✅ Examples: Stripe Secret Key (starts with `sk_`), Supabase Service Role Key

**⚠️ CRITICAL RULE:** Private keys must ALWAYS be stored in Lovable's Secrets Manager, never in your code or prompts!

**How Lovable Protects Keys:**
- Keys stored in **Cloud → Secrets**
- Accessed only through **Edge Functions** (server-side)
- Never exposed to frontend
- Encrypted and secure

### Common APIs You Might Use

- **Weather APIs** - Show weather data
- **Maps APIs** - Show locations
- **Social Media APIs** - Share to social platforms
- **Payment APIs** - Process payments
- **Email APIs** - Send emails
- **Analytics APIs** - Track usage

**💡 Beginner Tip:** Start with simple, public APIs to learn. Then move to authenticated APIs when needed.

---

## 📖 Lesson 6: Security Best Practices

### Why Security Matters

**Security** protects your app and users from:
- Unauthorized access
- Data breaches
- Payment fraud
- Malicious attacks

**Building secure apps is essential!** Even beginners need to understand security basics.

### How Lovable Handles Security

**Good news:** Lovable handles many security concerns automatically! But you still need to follow best practices.

#### Automatic Security Features

Lovable automatically:
- ✅ **Hashes passwords** - Passwords are never stored in plain text
- ✅ **Protects API keys** - Keys stored securely in secrets manager
- ✅ **Uses HTTPS** - All connections are encrypted
- ✅ **Validates inputs** - Prevents common attacks
- ✅ **Manages sessions** - Secure user sessions

**You don't need to code these!** Lovable does it for you.

### Security Best Practices

#### 1. Protecting API Keys

**❌ NEVER Do This:**
```
Add my Stripe key: sk_live_1234567890
```

**❌ NEVER Put Keys in Prompts:**
```
Use API key abc123xyz in the code
```

**✅ ALWAYS Do This:**
1. **Store keys in Secrets Manager:**
   - Go to **Cloud** → **Secrets**
   - Add your key
   - Give it a name (e.g., "STRIPE_SECRET_KEY")
   - Save

2. **Reference keys by name:**
   ```
   Use the Stripe connector I've configured in settings
   ```

3. **Lovable accesses keys securely:**
   - Keys stay in secrets manager
   - Accessed only server-side
   - Never exposed to frontend

**Example - Correct Way:**
```
1. Add Stripe Secret Key to Cloud → Secrets (name it STRIPE_SECRET_KEY)
2. Then ask: "Add Stripe payment processing using the configured Stripe connector"
```

#### 2. Password Security

**How Lovable Handles Passwords:**

- ✅ **Automatic hashing** - Passwords are hashed (encrypted) before storage
- ✅ **Never stored in plain text** - You can't see actual passwords
- ✅ **Secure comparison** - Passwords verified securely
- ✅ **Best practices built-in** - No need to code this yourself

**What You Should Do:**
- ✅ Require strong passwords (Lovable can enforce this)
- ✅ Use password confirmation fields
- ✅ Add password reset functionality
- ✅ Never log or display passwords

**Example Prompt:**
```
Add password requirements: minimum 8 characters, must include uppercase, lowercase, and number
```

#### 3. Rate Limiting

**What is Rate Limiting?**

Rate limiting prevents abuse by limiting how many requests a user can make.

**Why It Matters:**
- Prevents spam
- Stops brute force attacks
- Protects your resources
- Keeps costs down

**How Lovable Handles It:**

Lovable Cloud includes rate limiting automatically:
- ✅ Limits login attempts
- ✅ Prevents API abuse
- ✅ Protects against attacks
- ✅ Configurable limits

**What You Can Do:**
```
Add rate limiting to the contact form: maximum 5 submissions per hour per user
```

#### 4. Input Validation

**What is Input Validation?**

Checking that user input is safe and correct before using it.

**Why It Matters:**
- Prevents malicious code injection
- Ensures data is correct format
- Protects your database
- Improves user experience

**How Lovable Handles It:**

Lovable automatically:
- ✅ Validates form inputs
- ✅ Sanitizes user data
- ✅ Prevents SQL injection
- ✅ Blocks malicious code

**What You Should Do:**
- ✅ Specify validation requirements in prompts
- ✅ Test forms with invalid data
- ✅ Add helpful error messages

**Example:**
```
Create a contact form with validation:
- Email must be valid email format
- Name must be at least 2 characters
- Message must be between 10 and 1000 characters
- Show clear error messages for invalid inputs
```

#### 5. User Authentication Security

**Best Practices:**

**✅ Do:**
- Use strong password requirements
- Implement session timeouts
- Add "Remember Me" securely
- Use HTTPS (automatic with Lovable)
- Log out users after inactivity

**❌ Don't:**
- Store passwords in plain text (Lovable prevents this)
- Show password errors that reveal if email exists
- Allow unlimited login attempts
- Store sensitive data in frontend

**Example Prompts:**
```
Add session timeout: log users out after 30 minutes of inactivity
```

```
Add login attempt limiting: lock account after 5 failed attempts
```

#### 6. Data Protection

**What to Protect:**
- User personal information
- Payment data
- API keys and secrets
- Authentication tokens

**How to Protect:**

**✅ Use Environment Variables:**
- Store sensitive config in secrets
- Never hard-code sensitive data
- Use different keys for development/production

**✅ Encrypt Sensitive Data:**
- Lovable encrypts data in transit (HTTPS)
- Database encryption handled automatically
- File storage is secure

**✅ Limit Data Access:**
```
Make sure users can only see and edit their own data, not other users' data
```

#### 7. API Security

**For Public APIs:**
- ✅ Usually safe to use directly
- ✅ No authentication needed
- ✅ Limited functionality
- ⚠️ Still validate responses

**For Private APIs:**
- ✅ **ALWAYS** use secrets manager
- ✅ **NEVER** put keys in code
- ✅ Use Edge Functions (Lovable does this)
- ✅ Validate all API responses

**Example - Secure API Integration:**
```
1. Add OpenWeatherMap API key to Cloud → Secrets (name it WEATHER_API_KEY)
2. Then: "Integrate OpenWeatherMap API using the key in secrets. Create a weather widget that fetches current weather for a city."
```

### Security Checklist

Before deploying your app, check:

- [ ] All API keys are in secrets manager (not in code)
- [ ] Passwords have requirements enforced
- [ ] User data is protected (users can't access others' data)
- [ ] Forms have validation
- [ ] Rate limiting is enabled (if needed)
- [ ] Error messages don't reveal sensitive info
- [ ] HTTPS is enabled (automatic with Lovable)
- [ ] Authentication is working correctly
- [ ] No sensitive data in frontend code

### Common Security Mistakes to Avoid

**❌ Mistake 1: Putting API Keys in Prompts**
```
Add Stripe with key sk_live_12345
```
**✅ Fix:** Store in secrets, reference by name

**❌ Mistake 2: No Input Validation**
```
Create a form (no validation mentioned)
```
**✅ Fix:** Always specify validation requirements

**❌ Mistake 3: Exposing User Data**
```
Show all users' data to everyone
```
**✅ Fix:** Restrict data access to owners

**❌ Mistake 4: Weak Passwords**
```
Allow any password
```
**✅ Fix:** Require strong passwords

**❌ Mistake 5: No Rate Limiting**
```
Allow unlimited form submissions
```
**✅ Fix:** Add rate limiting for public forms

### Getting Help with Security

If you're unsure about security:

1. **Ask Chat Mode:**
   ```
   I'm adding payment processing. What security measures should I have in place?
   ```

2. **Check Documentation:**
   - Lovable security docs
   - Service-specific security guides (Stripe, Supabase, etc.)

3. **Test Thoroughly:**
   - Try to break your own app
   - Test with invalid inputs
   - Check error handling

**💡 Beginner Tip:** Don't worry about implementing security code yourself! Lovable handles most of it. Just follow best practices in how you use it.

---

## 🛠️ Hands-On Practice: Adding Authentication

Let's add user authentication to a project!

### Practice: Add User Authentication

#### Step 1: Enable Backend

Ask Lovable:
```
Enable Lovable Cloud for this project
```

Or if using Supabase:
```
Connect Supabase for authentication and database
```

#### Step 2: Add Authentication

Ask Lovable:
```
Add user authentication with:
- Sign up page with email and password
- Login page
- Logout functionality
- Protected routes (pages only logged-in users can see)
```

#### Step 3: Test It

1. **Try signing up:**
   - Go to the sign up page
   - Enter email and password
   - Submit
   - You should be logged in!

2. **Try logging out:**
   - Click logout
   - You should be logged out

3. **Try logging in:**
   - Go to login page
   - Enter your credentials
   - You should be logged in!

#### Step 4: Customize It

Ask for improvements:
```
Make the login page match my brand colors
Add "Remember me" checkbox to login
Add password reset functionality
```

**🎉 Congratulations!** You just added authentication to your app!

---

## 🛠️ Hands-On Practice: Adding a Database

Let's add a database to store data!

### Practice: Add Database for Blog Posts

#### Step 1: Enable Database

If using Lovable Cloud:
```
Add a database to store blog posts
```

If using Supabase:
```
Set up Supabase database for blog posts
```

#### Step 2: Define Your Data Structure

Ask Lovable:
```
Create a database table for blog posts with:
- Title (text)
- Content (text)
- Author (text)
- Date published (date)
- Featured image (image URL)
```

#### Step 3: Create Pages to Use the Database

Ask Lovable:
```
Create a blog listing page that shows all posts from the database
```

```
Create a blog post detail page that shows a single post
```

```
Create an admin page to add new blog posts to the database
```

#### Step 4: Test It

1. **Add a post:**
   - Go to admin page
   - Fill in the form
   - Submit
   - Post should be saved!

2. **View posts:**
   - Go to blog listing page
   - See your posts!

3. **View single post:**
   - Click on a post
   - See the full post!

**🎉 Congratulations!** You just added a database to your app!

---

## 🛠️ Mini-Project: Adding Stripe Subscription Payments

Let's build a complete subscription page with Stripe! This demonstrates connectors in practice.

### Project Goal

Create a subscription page where users can:
- See subscription plans
- Subscribe to a monthly plan
- Process payment securely with Stripe
- See subscription status

### Step 1: Set Up Stripe Account

**Before starting:**
1. Sign up at [stripe.com](https://stripe.com) (free to start)
2. Go to **Developers** → **API keys**
3. Get your **test keys** (for development):
   - **Publishable Key** (starts with `pk_test_`)
   - **Secret Key** (starts with `sk_test_`)

**💡 Note:** Use test keys for development. Switch to live keys when ready for production.

### Step 2: Configure Stripe in Lovable

1. **Go to Settings** → **Integrations** → **Connectors**
2. **Click "Add Connector"**
3. **Select "Stripe"**
4. **Enter your keys:**
   - Publishable Key: `pk_test_...` (your test key)
   - Secret Key: `sk_test_...` (your test key)
5. **Save**

**⚠️ Security Reminder:** Keys are stored securely in Lovable's secrets manager, not in your code!

### Step 3: Create Subscription Plans Page

Ask Lovable:
```
Create a subscription plans page with:
- Header: "Choose Your Plan"
- Three subscription tiers:
  1. Basic - $9.99/month - "Perfect for individuals"
  2. Pro - $19.99/month - "Best for professionals"  
  3. Enterprise - $49.99/month - "For teams and businesses"
- Each plan should have a "Subscribe" button
- Use a clean, modern card layout
- Make it responsive for mobile
```

### Step 4: Add Stripe Checkout

Ask Lovable:
```
Add Stripe Checkout to the subscription page. When a user clicks "Subscribe" on a plan:
- Open Stripe Checkout for that plan's price
- Use the Stripe connector I've configured
- After successful payment, redirect to a success page
- Store the subscription in the database with user ID and plan type
```

### Step 5: Create Success Page

Ask Lovable:
```
Create a subscription success page that:
- Shows a success message
- Displays the plan the user subscribed to
- Has a "Go to Dashboard" button
- Looks professional and celebratory
```

### Step 6: Add Subscription Management

Ask Lovable:
```
Create a "My Subscription" page that:
- Shows the user's current subscription plan
- Displays subscription status (active, canceled, etc.)
- Shows next billing date
- Has a "Manage Subscription" button that links to Stripe customer portal
- Only accessible to logged-in users
```

### Step 7: Secure the Implementation

Ask Lovable:
```
Make sure the subscription implementation is secure:
- All payment processing happens server-side
- Stripe keys are only accessed through secrets manager
- User can only see their own subscription
- Add proper error handling for failed payments
```

### Step 8: Test the Flow

**Testing Steps:**

1. **Test Subscription:**
   - Go to subscription page
   - Click "Subscribe" on a plan
   - Use Stripe test card: `4242 4242 4242 4242`
   - Use any future expiry date (e.g., 12/25)
   - Use any 3-digit CVC
   - Complete checkout
   - Should redirect to success page

2. **Test Subscription Page:**
   - Go to "My Subscription"
   - Should show your active plan
   - Should show next billing date

3. **Test Security:**
   - Try accessing another user's subscription (should fail)
   - Check that keys aren't in frontend code
   - Verify payment processing is secure

### Step 9: Add Polish

Ask Lovable:
```
Improve the subscription experience:
- Add loading states during payment processing
- Show clear error messages if payment fails
- Add confirmation before subscribing
- Improve the design and user experience
- Add email confirmation after successful subscription
```

### What You Learned

This mini-project taught you:
- ✅ How to configure Stripe connector
- ✅ How to use connectors in prompts
- ✅ How to process payments securely
- ✅ How to store subscription data
- ✅ Security best practices for payments
- ✅ Real-world payment integration

### Common Issues and Solutions

**Issue: "Stripe not working"**
- Check that keys are in Connectors settings
- Verify you're using test keys for testing
- Make sure Lovable Cloud is enabled

**Issue: "Payment not processing"**
- Check Stripe dashboard for errors
- Verify keys are correct
- Test with Stripe test cards

**Issue: "Subscription not saving"**
- Check database is set up
- Verify user authentication is working
- Check that subscription data is being stored

**💡 Pro Tip:** Always test with Stripe test mode first! Use test cards and test keys before going live.

---

## 🎯 Module 6 Challenges

**Build your backend skills with these progressive challenges!**

### Challenge 1: Basic Database Feature (Beginner)

**Your Task:** Build a comments system for a blog using Lovable Cloud.

**Requirements:**
- Create a database table for comments
- Comments should have: author name, comment text, date, and post ID
- Create a form to add comments
- Display comments below blog posts
- Only show comments for the current post

**💡 Hints:**
- Enable Lovable Cloud first
- Define your database structure clearly
- Link comments to posts using post ID
- Test adding and viewing comments

**Check your solution:** See [Challenge Solutions](supplement-challenge-solutions.md#module-6-challenge-1)

---

### Challenge 2: Extend with Email Notifications (Intermediate)

**Your Task:** Extend the comments system from Challenge 1 by adding email notifications using Resend connector.

**Requirements:**
- When someone adds a comment, send an email to the blog post author
- Email should include: commenter name, comment text, link to the post
- Configure Resend connector properly
- Store email in secrets manager (not in code!)

**💡 Hints:**
- Set up Resend account and get API key
- Add Resend connector in Lovable settings
- Store API key in secrets manager
- Use Resend to send email when comment is created

**Check your solution:** See [Challenge Solutions](supplement-challenge-solutions.md#module-6-challenge-2)

---

### Challenge 3: Secure User Data (Advanced)

**Your Task:** Build a user profile system with proper security.

**Requirements:**
- Users can create profiles with: name, bio, avatar
- Users can only view and edit their own profile
- Add authentication (sign up/login)
- Protect profile pages (only owner can access)
- Store profile data securely

**💡 Hints:**
- Enable authentication first
- Link profiles to user IDs
- Add authorization checks
- Test that users can't access others' profiles

**Check your solution:** See [Challenge Solutions](supplement-challenge-solutions.md#module-6-challenge-3)

---

### Challenge 4: Complete Feature with API Integration (Expert)

**Your Task:** Build a "Contact Us" feature that:
- Has a contact form (name, email, message)
- Stores submissions in database
- Sends email notification using Resend
- Integrates with a maps API to show your location
- Has rate limiting (max 3 submissions per hour)

**💡 Hints:**
- Use Lovable Cloud for database
- Configure Resend connector
- Use a public maps API (like Google Maps)
- Add rate limiting to prevent spam
- Test the complete flow

**Check your solution:** See [Challenge Solutions](supplement-challenge-solutions.md#module-6-challenge-4)

---

**💡 Pro Tip:** Start with Challenge 1, test it thoroughly, then move to the next. Each challenge builds on the previous one!

---

## ✅ Module 6 Checklist

Before moving to Module 7, make sure you can:

- [ ] Explain what "full-stack" means
- [ ] Enable Lovable Cloud
- [ ] Understand what connectors are
- [ ] Know when to use different backend options
- [ ] Add authentication to a project
- [ ] Add a database to a project
- [ ] Understand how to integrate APIs
- [ ] Store API keys securely in secrets manager
- [ ] Understand the difference between public and private API keys
- [ ] Follow security best practices
- [ ] Configure and use connectors (Stripe, Supabase)
- [ ] Understand how Lovable handles security automatically

---

## 🤔 Common Questions (FAQ)

### Q: Do I need to know how to set up databases?
**A:** No! Lovable handles it for you. Just describe what data you want to store.

### Q: Which backend should I use?
**A:** Start with Lovable Cloud - it's the easiest. Add connectors if you need specific features.

### Q: Are API keys safe?
**A:** Yes! Lovable stores them securely and uses Edge Functions to protect them.

### Q: Do I need to pay for these services?
**A:** Many have free tiers to start. Check each service's pricing.

### Q: Can I use multiple backends?
**A:** Usually you pick one main backend, but you can use connectors for specific features.

### Q: What if I don't need a backend?
**A:** That's fine! Simple websites don't always need backends. Add one when you need user accounts or data storage.

### Q: Where should I store my API keys?
**A:** ALWAYS in Lovable's Secrets Manager (Cloud → Secrets). NEVER in your code or prompts. Lovable handles the security for you.

### Q: What's the difference between public and private API keys?
**A:** Public keys (like Stripe Publishable Key) are safe for frontend. Private keys (like Stripe Secret Key) must stay in secrets manager and never be exposed.

### Q: Does Lovable handle password security?
**A:** Yes! Lovable automatically hashes passwords, so they're never stored in plain text. You don't need to code this yourself.

### Q: How do I know if my app is secure?
**A:** Use the security checklist in this module. Lovable handles most security automatically, but you should follow best practices like storing keys in secrets.

### Q: Can I put my Stripe key directly in a prompt?
**A:** NO! Never put private keys in prompts. Store them in Secrets Manager, then reference the connector in your prompts.

### Q: What if I accidentally exposed an API key?
**A:** Immediately revoke it in the service's dashboard and create a new one. Then update it in Lovable's secrets manager.

---

## 🎯 What's Next?

Fantastic work! You now understand how to add powerful backend features to your applications. You can:
- Use Lovable Cloud for built-in backend
- Add connectors for external services
- Integrate APIs securely
- Add authentication
- Add databases
- Follow security best practices
- Build payment integrations

**Ready for Module 7?** In the next module, we'll learn about Code Mode - viewing and editing code directly (optional for beginners, but useful to know about)!

---

## 💡 Pro Tips for Beginners

1. **Start with Lovable Cloud** - It's the easiest way to add backend features

2. **Add features gradually** - Don't try to add everything at once

3. **Test as you go** - Make sure things work before adding more

4. **Use connectors when needed** - They add powerful features easily

5. **Keep API keys safe** - ALWAYS store in secrets manager, NEVER in code or prompts

6. **Start simple** - Basic authentication and database first, then add complexity

7. **Follow security practices** - Lovable handles most security, but you need to use it correctly

8. **Test with test keys first** - Always use test mode (Stripe test keys, etc.) before going live

9. **Understand public vs. private keys** - Know which keys are safe for frontend and which must stay secret

---

*Module 6 Complete! 🎉*

