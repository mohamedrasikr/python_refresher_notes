# **Day 4 — Student Assignment**

## **Instructions**

This assignment focuses on modules, exception handling, and HTTP requests. These are crucial skills for building robust applications that interact with external services.

**How to approach this:**

1. Read each task carefully
2. Write your code in a Python file (e.g., `day4_tasks.py`)
3. Install requests library: `pip install requests`
4. Test your code thoroughly
5. Handle errors gracefully
6. For the mini project, create a separate file

**Important Notes:**

- Always use try/except for error handling
- Check HTTP response status codes
- Use meaningful error messages
- Test with both valid and invalid inputs
- Handle edge cases

---

## **Tasks**

### **Task 1: Working with Modules**

Write a program that:

1. Imports `math`, `random`, and `datetime` modules
2. Uses `math` to calculate:
   - Square root of 144
   - Area of a circle with radius 5
   - Factorial of 5
3. Uses `random` to:
   - Generate 5 random integers between 1 and 100
   - Pick a random item from a list of colors
   - Shuffle a list of numbers
4. Uses `datetime` to:
   - Display current date and time
   - Calculate date 7 days from now
   - Format date as "YYYY-MM-DD"

Display all results clearly.

---

### **Task 2: Exception Handling Basics**

Create a program that:

1. Asks the user to enter two numbers
2. Uses try/except to handle:
   - `ValueError` if input is not a number
   - `ZeroDivisionError` if dividing by zero
3. Performs these operations safely:
   - Addition
   - Subtraction
   - Multiplication
   - Division
4. Displays results or appropriate error messages
5. Uses a loop to allow multiple calculations

---

### **Task 3: File Operations with Error Handling**

Write a program that:

1. Asks the user for a filename
2. Tries to open and read the file
3. Handles these exceptions:
   - `FileNotFoundError` - file doesn't exist
   - `PermissionError` - no permission to read
   - `IOError` - other I/O errors
4. If file exists, displays:
   - Number of lines
   - Number of words
   - Number of characters
5. Uses `finally` to ensure proper cleanup

---

### **Task 4: HTTP GET Request**

Write a program that:

1. Makes a GET request to: `https://jsonplaceholder.typicode.com/posts/1`
2. Handles exceptions:
   - Connection errors
   - Timeout errors
   - HTTP errors
3. If successful:
   - Parse the JSON response
   - Display the post title and body
   - Extract and display the user ID
4. Use appropriate error messages for each error type

---

### **Task 5: HTTP POST Request**

Create a program that:

1. Creates a new "post" with this data:
   - title: "My Test Post"
   - body: "This is a test post"
   - userId: 1
2. Makes a POST request to: `https://jsonplaceholder.typicode.com/posts`
3. Handles all possible errors
4. If successful:
   - Display the created post ID
   - Display the response status code
   - Show the complete response data

---

### **Task 6: Combining Concepts**

Build a simple API client that:

1. Uses a while loop for a menu:
   - Option 1: Fetch a post by ID (GET)
   - Option 2: Create a new post (POST)
   - Option 3: Exit
2. For GET:
   - Ask user for post ID
   - Make GET request
   - Display post data or error
3. For POST:
   - Ask user for title and body
   - Make POST request
   - Display created post or error
4. Use try/except for all HTTP operations
5. Use functions to organize code

---

## **Expected Output Section**

Each task should produce clear, readable output that demonstrates:

- Correct use of modules and their functions
- Proper exception handling with try/except blocks
- Successful HTTP GET and POST requests
- Graceful error handling with informative messages
- Clean formatting and organization

Make sure errors are handled gracefully and don't crash the program.

---

## **Submission Checklist**

Before considering your Day 4 assignment complete, make sure:

- [ ] All 6 tasks are completed and working
- [ ] Modules are imported and used correctly
- [ ] Exception handling is implemented for all risky operations
- [ ] HTTP requests work correctly
- [ ] Errors are handled gracefully with informative messages
- [ ] Code includes comments explaining logic
- [ ] Output is clean and readable
- [ ] No syntax errors
- [ ] You've tested with both valid and invalid inputs

**Good luck, and happy coding! 🚀**
