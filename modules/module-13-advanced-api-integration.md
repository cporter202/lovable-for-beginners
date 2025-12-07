# Module 13: Advanced API Integration

**Goal:** Master integrating external APIs beyond basic connectors

**Estimated Time:** 45-60 minutes

**Prerequisites:** Complete Modules 1-6 first

---

## 🎯 What You'll Learn in This Module

By the end of this module, you will:
- Understand server-side vs. client-side API calls
- Know how to integrate public APIs
- Learn how to securely integrate private APIs
- Understand asynchronous data handling
- Be able to display API data effectively
- Know how to handle API errors
- Build real API integrations

---

## 📖 Lesson 1: Server-Side vs. Client-Side API Calls

### What's the Difference?

**Client-Side API Calls:**
- Made from the browser (frontend)
- User's browser makes the request
- API key might be visible (if public key)
- Limited to public APIs or APIs with CORS enabled

**Server-Side API Calls:**
- Made from the server (backend)
- Your server makes the request
- API keys stay secret (in secrets manager)
- Can use any API (public or private)

### When to Use Each

**Use Client-Side When:**
- ✅ Public API (no authentication)
- ✅ API supports CORS
- ✅ Simple data fetching
- ✅ Real-time updates needed

**Use Server-Side When:**
- ✅ Private API (requires secret keys)
- ✅ Sensitive data
- ✅ Rate limiting needed
- ✅ Data transformation required

### How Lovable Handles This

**Lovable automatically chooses:**
- **Public APIs** → Client-side (direct from browser)
- **Private APIs** → Server-side (via Edge Functions)

**You just ask:**
```
Integrate the [API name] API
```

Lovable figures out the best approach!

**💡 Beginner Tip:** Don't worry about the technical details! Lovable handles it. Just know that private keys stay secure.

---

## 📖 Lesson 2: Integrating Public APIs

### What are Public APIs?

**Public APIs** don't require authentication. Anyone can use them.

**Examples:**
- Weather data
- Public information
- Free services
- Open data

### How to Integrate Public APIs

#### Example 1: Weather API

**Simple Integration:**
```
Integrate the Open-Meteo weather API to show current weather for a city. 
API: https://api.open-meteo.com/v1/forecast
Display temperature, conditions, and a simple icon.
```

**More Detailed:**
```
Create a weather widget that:
- Uses Open-Meteo API (https://api.open-meteo.com/v1/forecast)
- Allows user to enter a city name
- Fetches current weather for that city
- Displays: temperature, conditions, humidity, wind speed
- Shows a weather icon based on conditions
- Updates when user searches for a new city
- Handles errors (city not found, API down)
```

#### Example 2: News API

**Integration:**
```
Integrate a news API to display recent articles:
- Fetch articles from https://newsapi.org/v2/top-headlines
- Display article title, description, image, and source
- Show 10 most recent articles
- Add "Load More" button for additional articles
- Handle API rate limits gracefully
```

#### Example 3: Random Data API

**Integration:**
```
Integrate the JSONPlaceholder API to create a demo data section:
- Fetch posts from https://jsonplaceholder.typicode.com/posts
- Display posts in a card layout
- Show post title and body
- Add pagination (10 posts per page)
```

### Best Practices for Public APIs

1. **Handle Errors:**
   ```
   Add error handling for the API:
   - Show message if API is down
   - Handle invalid responses
   - Display user-friendly error messages
   ```

2. **Add Loading States:**
   ```
   Show loading indicator while fetching data from the API
   ```

3. **Cache When Appropriate:**
   ```
   Cache API responses for 5 minutes to reduce API calls
   ```

**💡 Beginner Tip:** Public APIs are great for learning! Start with simple ones, then move to more complex integrations.

---

## 📖 Lesson 3: Integrating Private APIs Securely

### What are Private APIs?

**Private APIs** require authentication (API keys, tokens, etc.). They contain sensitive data or functionality.

**Examples:**
- Payment processing
- User data
- Email services
- Analytics

### How to Integrate Private APIs Securely

#### Step 1: Get Your API Key

1. Sign up for the service
2. Get your API key from their dashboard
3. **Keep it secret!** (Like a password)

#### Step 2: Store in Secrets Manager

**CRITICAL:** Never put API keys in prompts or code!

**✅ Correct Way:**
1. Go to **Cloud** → **Secrets**
2. Add your API key
3. Give it a name (e.g., "WEATHER_API_KEY")
4. Save

**❌ Wrong Way:**
```
Use API key: abc123xyz456
```
**NEVER DO THIS!**

#### Step 3: Reference in Your Prompt

**After storing in secrets:**
```
Integrate the OpenWeatherMap API using the key stored in secrets (WEATHER_API_KEY).
Create a weather widget that fetches current weather for a city.
Base URL: https://api.openweathermap.org/data/2.5
Endpoint: /weather?q={city}&appid={API_KEY}
```

**Lovable will:**
- Use the key from secrets
- Create Edge Function (server-side)
- Keep key secure
- Handle the API call

### Example: Secure API Integration

**Complete Workflow:**

1. **Add API Key to Secrets:**
   - Go to Cloud → Secrets
   - Add: `OPENWEATHER_API_KEY` = `your_key_here`
   - Save

2. **Integrate the API:**
   ```
   Integrate OpenWeatherMap API securely:
   - Use the API key from secrets (OPENWEATHER_API_KEY)
   - Create server-side function to fetch weather
   - Endpoint: GET /weather?q={city}&appid={API_KEY}
   - Create frontend widget that calls this function
   - Display: temperature, conditions, icon
   - Handle errors securely
   ```

3. **Lovable Creates:**
   - Edge Function (server-side, secure)
   - Frontend component (calls the function)
   - Error handling
   - All keys stay in secrets!

**💡 Beginner Tip:** Always use secrets manager for private APIs. It's the secure way!

---

## 📖 Lesson 4: Handling Asynchronous Data

### What is Asynchronous?

**Asynchronous** means things happen at different times, not all at once.

**Example:**
- User clicks button
- App requests data from API
- User can still interact (doesn't freeze)
- Data arrives later
- App updates with data

### How to Handle Async in Prompts

#### Pattern 1: Loading States

**Example:**
```
When fetching data from the API:
- Show loading spinner while fetching
- Display "Loading..." message
- Hide loading when data arrives
- Show data or error message
```

#### Pattern 2: Error Handling

**Example:**
```
Handle API errors gracefully:
- If API is down: Show "Service temporarily unavailable"
- If city not found: Show "City not found, please try another"
- If rate limited: Show "Too many requests, please wait"
- Always show user-friendly messages
```

#### Pattern 3: Retry Logic

**Example:**
```
If API call fails:
- Retry once after 2 seconds
- If still fails, show error message
- Allow user to manually retry
- Log errors for debugging
```

### Real Example: Weather Widget

**Complete Async Handling:**
```
Create a weather widget with:
- Input field for city name
- "Get Weather" button
- When clicked:
  - Show loading spinner
  - Fetch weather from API (async)
  - Display weather when data arrives
  - Show error if API fails
  - Allow user to search again
- Handle all states: loading, success, error
```

**💡 Beginner Tip:** Always ask for loading states and error handling. It makes your app feel professional!

---

## 📖 Lesson 5: Displaying API Data

### Best Practices for Displaying API Data

#### Pattern 1: Format Data Nicely

**Example:**
```
Display the weather data in a user-friendly format:
- Temperature: Show in large, readable font with °C or °F
- Conditions: Show as text and icon
- Date/Time: Format as "Today, 3:00 PM"
- Make it visually appealing with cards or widgets
```

#### Pattern 2: Handle Empty States

**Example:**
```
When no data is available:
- Show friendly message: "No weather data available"
- Provide instructions: "Enter a city name to get weather"
- Don't show errors, show helpful guidance
```

#### Pattern 3: Update Data

**Example:**
```
Make the weather data update:
- Refresh button to get latest data
- Auto-refresh every 5 minutes
- Show "Last updated" timestamp
- Indicate when data is fresh vs. stale
```

### Example: Complete API Integration

**Weather Dashboard:**
```
Create a weather dashboard that:
- Fetches weather from OpenWeatherMap API (key in secrets)
- Shows current weather for user's location
- Displays: temperature, conditions, humidity, wind
- Shows 5-day forecast
- Updates every hour
- Handles errors gracefully
- Shows loading states
- Responsive design for mobile
```

---

## 🛠️ Hands-On Practice: Build a Weather App

Let's build a complete weather application!

### Step 1: Set Up API

1. **Get API Key:**
   - Sign up at [openweathermap.org](https://openweathermap.org) (free tier available)
   - Get your API key

2. **Store in Secrets:**
   - Go to Cloud → Secrets
   - Add: `OPENWEATHER_API_KEY` = `your_key`
   - Save

### Step 2: Create Weather Widget

Ask Lovable:
```
Create a weather widget that:
- Has an input field for city name
- "Get Weather" button
- Fetches weather from OpenWeatherMap API using key from secrets
- Shows: temperature, conditions, humidity, wind speed
- Displays weather icon
- Shows loading state while fetching
- Handles errors (city not found, API down)
- Looks modern and clean
```

### Step 3: Add Forecast

Ask Lovable:
```
Add a 5-day weather forecast below the current weather:
- Show daily high/low temperatures
- Show conditions for each day
- Display in a horizontal scrollable list
- Make it visually appealing
```

### Step 4: Add Features

Ask Lovable:
```
Enhance the weather app:
- Add "Use My Location" button (gets weather for current location)
- Add favorite cities (save 3 favorite cities)
- Add unit toggle (Celsius/Fahrenheit)
- Improve error messages
- Add refresh functionality
```

### Step 5: Test and Debug

1. **Test with valid cities:**
   - Enter "London"
   - Enter "New York"
   - Verify data displays

2. **Test error handling:**
   - Enter invalid city
   - See error message
   - Verify it's user-friendly

3. **Test on mobile:**
   - Check responsive design
   - Test all features

**🎉 Congratulations!** You built a complete API integration!

---

## ✅ Module 13 Checklist

Before completing the course, make sure you can:

- [ ] Understand server-side vs. client-side API calls
- [ ] Integrate public APIs
- [ ] Securely integrate private APIs
- [ ] Store API keys in secrets manager
- [ ] Handle asynchronous data
- [ ] Display API data effectively
- [ ] Handle API errors
- [ ] Build complete API integrations

---

## 🤔 Common Questions (FAQ)

### Q: How do I know if an API is public or private?
**A:** Check the API documentation. If it requires an API key for all requests, it's private. If some endpoints work without keys, those are public.

### Q: Can I use multiple APIs in one app?
**A:** Yes! You can integrate as many APIs as you need. Just store each key in secrets.

### Q: What if an API requires OAuth?
**A:** That's more complex. Ask Chat Mode: "How do I integrate an API that requires OAuth authentication?"

### Q: How do I handle API rate limits?
**A:** Ask Lovable to implement rate limiting and caching. Also check the API's documentation for limits.

### Q: Can I test APIs before integrating?
**A:** Yes! Many APIs have test endpoints or sandbox modes. Test with those first.

---

## 🎯 What's Next?

Fantastic! You now understand advanced API integration. You can build apps that connect to external services securely and effectively.

**Continue with:**
- Module 14: Version Control with GitHub
- Or apply these skills to your capstone project!

---

*Module 13 Complete! 🎉*

