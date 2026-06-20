# **Day 5 — Mini Project**

## **Project Overview**

Build a CSV-based Student Score Manager that allows you to manage student records, calculate statistics, and export data. This project combines CSV file operations, data processing, and user interaction.

---

## **Project Requirements**

Your program must:

1. **Display a main menu** with options

2. **Add student records**:
   - Student name
   - Student ID
   - Scores for 3 subjects (Math, Science, English)
   - Save to CSV file

3. **View all students**:
   - Read from CSV file
   - Display in formatted table
   - Show individual scores and averages

4. **Calculate statistics**:
   - Class average for each subject
   - Overall class average
   - Highest and lowest scores per subject
   - Number of students

5. **Search student**:
   - Search by name or ID
   - Display student details

6. **Update student**:
   - Find student by ID
   - Update scores
   - Save back to CSV

7. **Export data**:
   - Export to JSON format
   - Export summary statistics to text file

8. **Error handling**:
   - Handle missing CSV file (create if doesn't exist)
   - Validate input (scores 0-100)
   - Handle file errors gracefully

---

## **Step-by-Step Instructions**

1. **Set up your file**
   - Create `student_manager.py`
   - Import `csv`, `json`, `os`
   - Add comment header

2. **Create helper functions**
   - `load_students()` - Read CSV, return list of dictionaries
   - `save_students(students)` - Write list to CSV
   - `add_student()` - Get input, add to list, save
   - `display_students(students)` - Format and show all
   - `calculate_stats(students)` - Compute statistics
   - `search_student(students, query)` - Find by name/ID
   - `update_student(students, student_id)` - Modify scores
   - `export_to_json(students)` - Save as JSON
   - `export_summary(stats)` - Save stats to text file

3. **CSV structure**
   - Headers: StudentID, Name, Math, Science, English
   - Use `csv.DictReader` and `csv.DictWriter`

4. **Implement main menu**
   - Use while loop
   - Get user choice
   - Call appropriate functions

5. **Add student function**
   - Get input for all fields
   - Validate scores (0-100)
   - Create dictionary
   - Append to list
   - Save to CSV

6. **View students function**
   - Load from CSV
   - Calculate average for each student
   - Display in formatted table

7. **Statistics function**
   - Load students
   - Calculate class averages
   - Find min/max per subject
   - Display formatted results

8. **Search function**
   - Load students
   - Search by name (case-insensitive) or ID
   - Display matching students

9. **Update function**
   - Find student by ID
   - Get new scores
   - Update dictionary
   - Save to CSV

10. **Export functions**
    - JSON: Convert list of dicts to JSON, save with indent
    - Summary: Write statistics to text file

11. **Error handling**
    - Check if CSV exists, create with headers if not
    - Validate all inputs
    - Handle file errors

12. **Test thoroughly**
    - Add multiple students
    - Test all functions
    - Verify CSV file is correct
    - Test error cases

---

## **Example Interaction / Output**

```
╔══════════════════════════════════════╗
║   Student Score Manager             ║
╚══════════════════════════════════════╝

Menu:
1. Add student
2. View all students
3. Calculate statistics
4. Search student
5. Update student scores
6. Export to JSON
7. Export summary
8. Exit

Enter your choice: 1

Enter Student ID: S001
Enter Name: Alice Johnson
Enter Math score (0-100): 85
Enter Science score (0-100): 90
Enter English score (0-100): 88

Student added successfully!

Enter your choice: 2

═══════════════════════════════════════
All Students:
═══════════════════════════════════════
ID    Name            Math  Science  English  Average
S001  Alice Johnson   85    90       88       87.67
S002  Bob Smith       78    82       80       80.00
S003  Charlie Brown   92    95       90       92.33
═══════════════════════════════════════

Enter your choice: 3

═══════════════════════════════════════
Class Statistics:
═══════════════════════════════════════
Total Students: 3

Subject Averages:
  Math:    85.00
  Science: 89.00
  English: 86.00

Overall Average: 86.67

Highest Scores:
  Math:    92 (Charlie Brown)
  Science: 95 (Charlie Brown)
  English: 90 (Charlie Brown, Alice Johnson)

Lowest Scores:
  Math:    78 (Bob Smith)
  Science: 82 (Bob Smith)
  English: 80 (Bob Smith)
═══════════════════════════════════════

Enter your choice: 8
Goodbye!
```

**Note:** Your output format can vary, but it should be clear and organized.

---

## **Bonus Challenges (Optional)**

1. **Delete student**: Remove student from CSV
2. **Sort students**: Sort by name, ID, or average score
3. **Grade assignment**: Automatically assign letter grades
4. **Data validation**: More robust input validation
5. **Backup**: Create backup copies of CSV file
6. **Import**: Import students from JSON file
7. **Charts**: Generate simple text-based charts for statistics
8. **Multiple classes**: Support multiple class sections

---

## **Tips & Hints**

- **CSV file structure:**
  ```python
  # Headers
  fieldnames = ["StudentID", "Name", "Math", "Science", "English"]
  
  # Writing
  with open("students.csv", "w", newline="") as file:
      writer = csv.DictWriter(file, fieldnames=fieldnames)
      writer.writeheader()
      writer.writerows(students)
  ```

- **Check if file exists:**
  ```python
  import os
  if not os.path.exists("students.csv"):
      # Create file with headers
  ```

- **Calculate average:**
  ```python
  scores = [int(student["Math"]), int(student["Science"]), int(student["English"])]
  average = sum(scores) / len(scores)
  ```

- **Search function:**
  ```python
  def search_student(students, query):
      results = []
      for student in students:
          if query.lower() in student["Name"].lower() or query == student["StudentID"]:
              results.append(student)
      return results
  ```

- **Update function:**
  ```python
  for i, student in enumerate(students):
      if student["StudentID"] == student_id:
          # Update student[i]
          break
  ```

- **Formatting table**: Use string formatting for aligned columns
- **Error handling**: Wrap file operations in try/except
- **Validation**: Check scores are between 0-100

---

**Good luck building your student manager!**

