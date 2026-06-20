# **Day 4 — Mini Project**

## **Project Overview**

Build an API Data Fetcher that fetches data from a public API, handles errors gracefully, and displays information in a user-friendly way. This project combines HTTP requests, exception handling, and data processing.

---

## **Project Requirements**

Your program must:

1. **Display a welcome message** and menu

2. **Fetch user data** from API:
   - Endpoint: `https://jsonplaceholder.typicode.com/users`
   - Display list of users with IDs and names
   - Allow user to select a user by ID

3. **Display user details**:
   - Name, username, email
   - Address (street, city, zipcode)
   - Phone number
   - Company name

4. **Fetch user's posts**:
   - Endpoint: `https://jsonplaceholder.typicode.com/posts?userId={id}`
   - Display post titles
   - Allow viewing full post content

5. **Error handling**:
   - Handle connection errors
   - Handle timeout errors
   - Handle HTTP errors (404, 500, etc.)
   - Handle JSON parsing errors
   - Display user-friendly error messages

6. **Menu options**:
   - View all users
   - View user details
   - View user's posts
   - Exit

---

## **Step-by-Step Instructions**

1. **Set up your file**
   - Create `api_fetcher.py`
   - Import necessary modules: `requests`, `json`
   - Add comment header

2. **Create helper functions**
   - `fetch_users()` - GET request to fetch all users
   - `fetch_user_posts(user_id)` - GET request for user's posts
   - `display_users(users)` - Format and display user list
   - `display_user_details(user)` - Show user information
   - `display_posts(posts)` - Show posts

3. **Implement error handling**
   - Wrap all HTTP requests in try/except
   - Handle `requests.exceptions.RequestException`
   - Handle specific cases (timeout, connection, etc.)
   - Check status codes with `raise_for_status()`

4. **Create main menu**
   - Use while loop
   - Get user choice
   - Call appropriate functions

5. **Fetch and display users**
   - Make GET request to users endpoint
   - Parse JSON response
   - Display formatted list

6. **Fetch user details**
   - Get user ID from user
   - Find user in list
   - Display formatted details

7. **Fetch and display posts**
   - Get user ID
   - Make GET request with userId parameter
   - Display post titles
   - Allow viewing full post

8. **Test thoroughly**
   - Test with valid inputs
   - Test error scenarios
   - Test with invalid user IDs

---

## **Example Interaction / Output**

```
╔══════════════════════════════════════╗
║   API Data Fetcher                  ║
╚══════════════════════════════════════╝

Menu:
1. View all users
2. View user details
3. View user's posts
4. Exit

Enter your choice: 1

Fetching users...

═══════════════════════════════════════
All Users:
═══════════════════════════════════════
1. Leanne Graham (ID: 1)
2. Ervin Howell (ID: 2)
3. Clementine Bauch (ID: 3)
...

Enter your choice: 2

Enter user ID: 1

Fetching user details...

═══════════════════════════════════════
User Details:
═══════════════════════════════════════
Name: Leanne Graham
Username: Bret
Email: Sincere@april.biz
Address: 
  Street: Kulas Light
  City: Gwenborough
  Zipcode: 92998-3874
Phone: 1-770-736-8031 x56442
Company: Romaguera-Crona

Enter your choice: 3

Enter user ID: 1

Fetching posts...

Posts by Leanne Graham:
1. sunt aut facere repellat provident...
2. qui est esse
3. ea molestias quasi exercitationem...
...

View full post? (enter number or 'back'): 1

Title: sunt aut facere repellat provident occaecati excepturi optio reprehenderit
Body: quia et suscipit...

Enter your choice: 4
Goodbye!
```

**Note:** Your output format can vary, but it should be clear and organized.

---

## **Bonus Challenges (Optional)**

1. **Save data**: Save fetched user/post data to JSON files
2. **Search**: Search users by name or email
3. **Comments**: Fetch and display comments for posts
4. **Caching**: Cache API responses to avoid repeated requests
5. **Pagination**: Handle paginated API responses
6. **Export**: Export user data to CSV format
7. **Multiple APIs**: Integrate with another public API

---

## **Tips & Hints**

- **Error handling structure:**
  ```python
  try:
      response = requests.get(url, timeout=5)
      response.raise_for_status()
      data = response.json()
  except requests.exceptions.Timeout:
      print("Request timed out. Please try again.")
  except requests.exceptions.ConnectionError:
      print("Connection error. Check your internet.")
  except requests.exceptions.HTTPError as e:
      print(f"HTTP error: {e}")
  except requests.exceptions.RequestException as e:
      print(f"Request failed: {e}")
  ```

- **Finding user by ID:**
  ```python
  user = next((u for u in users if u["id"] == user_id), None)
  if user:
      # display user
  else:
      print("User not found")
  ```

- **URL parameters:**
  ```python
  params = {"userId": user_id}
  response = requests.get(url, params=params)
  ```

- **Formatting output**: Use f-strings for clean display
- **Menu loop**: Use `while True:` with `break` to exit
- **Validate input**: Check that user IDs are valid numbers
- **Timeout**: Always set timeout (e.g., `timeout=5`) to avoid hanging

---

**Good luck building your API fetcher!**

