# **Day 5 — Student Assignment**

## **Instructions**

This assignment focuses on file handling with text, JSON, and CSV files. You'll practice reading from and writing to different file formats.

**How to approach this:**
1. Read each task carefully
2. Create sample files for testing
3. Write your code in a Python file (e.g., `day5_tasks.py`)
4. Test with different file contents
5. Handle errors appropriately
6. For the mini project, create a separate file

**Important Notes:**
- Always use `with` statement for file operations
- Handle file errors (FileNotFoundError, PermissionError, etc.)
- Test with both existing and new files
- Use appropriate file modes (r, w, a)
- Format JSON output for readability

---

## **Tasks**

### **Task 1: Text File Operations**

Create a program that:
1. Writes a to-do list to `todo.txt` with at least 5 items
2. Reads the file and displays all items with line numbers
3. Asks the user to add a new item
4. Appends the new item to the file
5. Displays the updated list
6. Counts and displays the total number of items

Use proper error handling for file operations.

---

### **Task 2: JSON File Operations**

Create a program that:
1. Creates a dictionary with student data:
   - name, age, grades (list of 3 scores), email
   - Store at least 3 students
2. Saves the data to `students.json` with proper formatting (indent=4)
3. Reads the data back from the file
4. Calculates and displays average grade for each student
5. Finds and displays the student with the highest average
6. Updates one student's grade and saves back to file

---

### **Task 3: CSV File Operations**

Create a program that:
1. Writes a CSV file `products.csv` with columns:
   - Name, Price, Quantity, Category
   - Include at least 5 products
2. Reads the CSV file using `csv.DictReader`
3. Displays all products in a formatted way
4. Calculates and displays:
   - Total value (sum of price × quantity)
   - Average price
   - Products by category
5. Finds the most expensive and cheapest products

---

### **Task 4: File Conversion**

Write a program that:
1. Reads data from a text file `data.txt` (create it with some structured data)
2. Parses the data (you decide the format)
3. Converts it to JSON format
4. Saves as `data.json`
5. Also converts to CSV format
6. Saves as `data.csv`
7. Verifies by reading both files back

---

### **Task 5: Data Processing from Files**

Create a program that:
1. Reads a JSON file with employee data (create sample data):
   - name, department, salary, years_of_experience
2. Processes the data to:
   - Calculate average salary by department
   - Find employees with >5 years experience
   - Calculate total payroll
3. Writes results to a text file `report.txt` in a formatted way
4. Also exports filtered data (high experience employees) to CSV

---

### **Task 6: File Manager**

Build a simple file manager that:
1. Shows a menu:
   - Create new text file
   - Read existing file
   - Append to file
   - Delete file
   - List all .txt files in directory
   - Exit
2. Implements each option with proper error handling
3. Uses functions to organize code
4. Validates file existence before operations
5. Provides user-friendly messages

---

## **Expected Output Section**

Each task should produce clear, readable output that demonstrates:
- Successful file reading and writing operations
- Proper JSON parsing and creation
- Correct CSV file handling
- Appropriate error handling
- Clean formatting and organization

Make sure files are created, read, and modified correctly.

---

## **Submission Checklist**

Before considering your Day 5 assignment complete, make sure:

- [ ] All 6 tasks are completed and working
- [ ] Text files are read and written correctly
- [ ] JSON files are properly formatted and parsed
- [ ] CSV files are created and read correctly
- [ ] Error handling is implemented for all file operations
- [ ] Code uses `with` statement for file operations
- [ ] Code includes comments explaining logic
- [ ] Output is clean and readable
- [ ] No syntax errors
- [ ] You've tested with different file contents

**Good luck, and happy coding! 🚀**

