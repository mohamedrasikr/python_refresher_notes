# **Day 3 — Student Assignment**

## **Instructions**

This assignment focuses on while loops, list comprehensions, functions, and lambda functions. These concepts help you write more organized and efficient code.

**How to approach this:**
1. Read each task carefully
2. Write your code in a Python file (e.g., `day3_tasks.py`)
3. Test your code thoroughly
4. Make sure functions are reusable and well-documented
5. For the mini project, create a separate file

**Important Notes:**
- Use meaningful function names
- Add docstrings to explain what functions do
- Test functions with different inputs
- Use list comprehensions where appropriate
- Handle edge cases (empty lists, invalid inputs, etc.)

---

## **Tasks**

### **Task 1: while Loop Practice**

Write a program that:
1. Asks the user to guess a number between 1 and 100
2. Uses a while loop to keep asking until they guess correctly
3. Provides hints ("too high" or "too low")
4. Counts the number of attempts
5. Displays a congratulatory message with the attempt count

Use `random.randint(1, 100)` to generate the secret number (import random first).

---

### **Task 2: List Comprehensions**

Given the list: `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`

Use list comprehensions to create:
1. A list of squares: `[1, 4, 9, 16, ...]`
2. A list of even numbers only
3. A list of numbers greater than 5, each multiplied by 2
4. A list of strings: `["1", "2", "3", ...]`
5. A list of tuples: `[(1, 1), (2, 4), (3, 9), ...]` (number, square)

Display all results.

---

### **Task 3: Function Basics**

Create functions for:
1. `calculate_area(length, width)` - calculates rectangle area
2. `is_even(number)` - returns True if number is even, False otherwise
3. `get_grade(score)` - returns letter grade (A-F) based on score
4. `reverse_string(text)` - returns reversed string
5. `count_vowels(text)` - returns number of vowels in text

Test each function with different inputs and display results.

---

### **Task 4: Function with Multiple Returns**

Write a function `analyze_numbers(numbers)` that:
- Takes a list of numbers
- Returns a dictionary with:
  - "sum": sum of all numbers
  - "average": average of numbers
  - "max": maximum value
  - "min": minimum value
  - "count": number of items
  - "evens": count of even numbers
  - "odds": count of odd numbers

Test with: `[12, 45, 8, 23, 56, 9, 34, 67, 3, 91]`

---

### **Task 5: Lambda Functions**

Use lambda functions to:
1. Create a lambda that doubles a number
2. Create a lambda that checks if a number is positive
3. Use `map()` with lambda to convert `[1, 2, 3, 4, 5]` to `[2, 4, 6, 8, 10]`
4. Use `filter()` with lambda to get only positive numbers from `[-2, -1, 0, 1, 2, 3]`
5. Use `sorted()` with lambda to sort `["apple", "banana", "cherry"]` by length

Display all results.

---

### **Task 6: Combining Concepts**

Create a program that:
1. Defines a function `process_scores(scores)` that:
   - Takes a list of scores (0-100)
   - Uses list comprehension to calculate letter grades
   - Returns a list of tuples: `(score, grade)`
2. Uses a while loop to collect scores from user (until they type "done")
3. Validates that scores are between 0-100
4. Calls the function and displays results
5. Uses lambda to find the highest score
6. Displays statistics (average, max, min)

---

## **Expected Output Section**

Each task should produce clear, readable output that demonstrates:
- Correct while loop implementation
- Effective use of list comprehensions
- Well-defined functions with proper parameters and returns
- Appropriate use of lambda functions
- Clean formatting and organization

Make sure your functions are reusable and well-documented.

---

## **Submission Checklist**

Before considering your Day 3 assignment complete, make sure:

- [ ] All 6 tasks are completed and working
- [ ] Functions are properly defined with parameters
- [ ] Functions return appropriate values
- [ ] List comprehensions are used effectively
- [ ] Lambda functions are implemented correctly
- [ ] Code includes comments and docstrings
- [ ] Output is clean and readable
- [ ] No syntax errors
- [ ] You've tested with different inputs

**Good luck, and happy coding! 🚀**

