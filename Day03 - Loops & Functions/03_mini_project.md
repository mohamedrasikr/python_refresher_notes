# **Day 3 — Mini Project**

## **Project Overview**

Build a Quiz Creator application that allows users to create quizzes, take quizzes, and see results. This project will use functions to organize code, while loops for user interaction, and list comprehensions for data processing.

---

## **Project Requirements**

Your program must:

1. **Display a main menu** with options:
   - Create a new quiz
   - Take a quiz
   - View quiz results
   - Exit

2. **Create quiz function** that:
   - Asks for quiz name
   - Allows adding multiple questions
   - Each question has: question text, 4 options (A, B, C, D), correct answer
   - Stores questions in a list of dictionaries

3. **Take quiz function** that:
   - Shows available quizzes
   - Displays questions one by one
   - Collects user answers
   - Calculates score
   - Shows results

4. **View results function** that:
   - Shows quiz name
   - Shows user's score
   - Shows percentage
   - Shows which questions were correct/incorrect

5. **Use functions** to organize code:
   - `create_quiz()` - handles quiz creation
   - `take_quiz(quiz)` - handles taking a quiz
   - `display_results(quiz, answers, score)` - shows results
   - `calculate_score(quiz, answers)` - calculates score

6. **Data storage**: Use lists and dictionaries to store quiz data

---

## **Step-by-Step Instructions**

1. **Set up your file**
   - Create `quiz_creator.py`
   - Add comment header

2. **Create data structure**
   - Use a list to store quizzes
   - Each quiz is a dictionary with: name, questions
   - Each question is a dictionary with: question, options, correct_answer

3. **Implement main menu**
   - Use while loop for menu
   - Get user choice
   - Call appropriate function

4. **Create quiz function**
   - Get quiz name
   - Use while loop to add questions
   - For each question: get question text, 4 options, correct answer
   - Store in dictionary structure
   - Add to quizzes list

5. **Take quiz function**
   - Show available quizzes
   - Let user select one
   - Display questions one by one
   - Collect answers
   - Calculate and display score

6. **Helper functions**
   - `calculate_score()`: Compare answers, return score
   - `display_results()`: Format and show results
   - Use list comprehensions where helpful

7. **Test thoroughly**
   - Create multiple quizzes
   - Take quizzes
   - Verify scoring works correctly

---

## **Example Interaction / Output**

```
╔══════════════════════════════════════╗
║   Quiz Creator                       ║
╚══════════════════════════════════════╝

Menu:
1. Create a new quiz
2. Take a quiz
3. View quiz results
4. Exit

Enter your choice: 1

Enter quiz name: Python Basics

Add question? (yes/no): yes
Question: What is the output of print(2+3)?
Option A: 5
Option B: 23
Option C: Error
Option D: None
Correct answer (A/B/C/D): A

Add another question? (yes/no): yes
Question: Which keyword is used to define a function?
Option A: func
Option B: def
Option C: function
Option D: define
Correct answer (A/B/C/D): B

Add another question? (yes/no): no

Quiz 'Python Basics' created successfully!

Enter your choice: 2

Available quizzes:
1. Python Basics

Select quiz number: 1

=== Python Basics Quiz ===

Question 1: What is the output of print(2+3)?
A) 5
B) 23
C) Error
D) None
Your answer: A

Question 2: Which keyword is used to define a function?
A) func
B) def
C) function
D) define
Your answer: B

=== Results ===
Score: 2/2 (100%)
All answers correct!

Enter your choice: 4
Goodbye!
```

**Note:** Your output format can vary, but it should be clear and organized.

---

## **Bonus Challenges (Optional)**

1. **Save/Load**: Save quizzes to a file and load them back
2. **Timer**: Add a time limit for each question
3. **Multiple choice types**: Support true/false questions
4. **Quiz statistics**: Track average scores, most missed questions
5. **Edit quizzes**: Allow modifying existing quizzes
6. **Question bank**: Create a pool of questions and randomly select
7. **Export results**: Save quiz results to a file

---

## **Tips & Hints**

- **Data structure example:**
  ```python
  quiz = {
      "name": "Python Basics",
      "questions": [
          {
              "question": "What is 2+3?",
              "options": {"A": "5", "B": "6", "C": "7", "D": "8"},
              "correct": "A"
          },
          ...
      ]
  }
  ```

- **Function structure:**
  ```python
  def calculate_score(quiz, answers):
      correct = 0
      for i, question in enumerate(quiz["questions"]):
          if answers[i] == question["correct"]:
              correct += 1
      return correct
  ```

- **List comprehension for options:**
  ```python
  options_list = [f"{key}) {value}" for key, value in question["options"].items()]
  ```

- **Menu loop:**
  ```python
  while True:
      # show menu
      choice = input("Enter choice: ")
      if choice == "4":
          break
      # handle choices
  ```

- **Validate input**: Check that answers are A, B, C, or D
- **Use functions**: Break code into logical functions
- **Error handling**: Handle empty quizzes, invalid selections

---

**Good luck building your quiz creator!**

