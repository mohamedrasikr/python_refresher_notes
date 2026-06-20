# **Day 1 — Mini Project**

## **Project Overview**

Build a command-line application that collects and displays user information. This project combines all the concepts from Day 1: variables, data types, f-strings, user input, and operators. You'll create a simple but functional program that demonstrates your understanding of Python's building blocks.

---

## **Project Requirements**

Your program must:

1. **Welcome the user** with a friendly greeting

2. **Collect the following information:**
   - Full name (first and last, separately)
   - Age
   - Email address
   - Phone number
   - City of residence
   - Number of programming languages they know
   - Their favorite programming language
   - Years of coding experience
   - Whether they're currently a student (yes/no)

3. **Perform calculations:**
   - Calculate birth year (2024 - age)
   - Calculate average languages learned per year (if experience > 0)
   - Determine experience level:
     - Beginner: experience < 1 year
     - Intermediate: 1-3 years
     - Advanced: 3+ years

4. **Display a formatted summary** that includes:
   - All collected information
   - Calculated values
   - A personalized message based on their experience level

---

## **Step-by-Step Instructions**

1. **Set up your file**
   - Create a new Python file called `user_info_collector.py`
   - Add a comment at the top with your name and the project name

2. **Create the welcome message**
   - Use print statements to display a welcoming header
   - Make it visually appealing with borders or separators

3. **Collect user input**
   - Use `input()` to get each piece of information
   - Store each value in a descriptive variable name
   - Remember: `input()` returns strings, so convert age and numbers to integers/floats where needed

4. **Perform calculations**
   - Calculate birth year using arithmetic operators
   - Calculate average languages per year (handle division by zero!)
   - Use comparison operators to determine experience level

5. **Format and display the summary**
   - Use f-strings to create a nicely formatted output
   - Include all collected information
   - Show calculated values clearly
   - Add a personalized message based on experience level

6. **Test your program**
   - Run it with different inputs
   - Test edge cases (age 0, experience 0, etc.)
   - Make sure it doesn't crash

---

## **Example Interaction / Output**

```
╔════════════════════════════════════════╗
║   Welcome to User Info Collector!     ║
╚════════════════════════════════════════╝

Please provide the following information:

First Name: John
Last Name: Doe
Age: 25
Email: john.doe@email.com
Phone: 555-1234
City: San Francisco
Number of programming languages you know: 3
Your favorite programming language: Python
Years of coding experience: 2
Are you currently a student? (yes/no): yes

╔════════════════════════════════════════╗
║        USER INFORMATION SUMMARY        ║
╔════════════════════════════════════════╗
║ Name: John Doe                         ║
║ Age: 25 years old                      ║
║ Birth Year: 1999                       ║
║ Email: john.doe@email.com              ║
║ Phone: 555-1234                        ║
║ City: San Francisco                    ║
║                                        ║
║ Programming Experience:                ║
║   Languages Known: 3                   ║
║   Favorite Language: Python            ║
║   Years of Experience: 2               ║
║   Experience Level: Intermediate       ║
║   Avg Languages/Year: 1.5              ║
║   Student Status: Yes                  ║
║                                        ║
║ Message: Keep up the great work!       ║
╚════════════════════════════════════════╝
```

**Note:** Your output format can be different, but it should be clear, organized, and include all the required information.

---

## **Bonus Challenges (Optional)**

If you want to go further, try adding:

1. **Input validation**
   - Ensure age is a positive number
   - Check that email contains an @ symbol
   - Validate phone number format

2. **Enhanced features**
   - Add color to your output (explore libraries like `colorama`)
   - Save the collected information to a text file
   - Ask for additional information (country, occupation, etc.)
   - Add more calculations (days since birth, etc.)

3. **Better formatting**
   - Use different border styles
   - Add emojis or symbols
   - Create a more elaborate summary layout

---

## **Tips & Hints**

- **Type conversion matters:** When you get age from `input()`, it's a string. Convert it to `int()` before doing math.

- **Handle edge cases:** What happens if someone enters 0 for years of experience? Your division might break. Use conditional logic to handle this.

- **Boolean conversion:** When asking yes/no questions, you can convert the answer like this:
  ```python
  is_student = input("Are you a student? (yes/no): ").lower() == "yes"
  ```

- **Formatting with f-strings:** You can format numbers in f-strings:
  ```python
  f"Average: {avg:.2f}"  # Shows 2 decimal places
  ```

- **Empty lines:** Use `print()` or `print("\n")` to add spacing in your output.

- **Test as you go:** Don't wait until the end. Test each section as you build it.

- **Comments help:** Add comments explaining your logic, especially for calculations.

---

**Good luck building your first project!**

