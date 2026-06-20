# **Day 6 — Student Assignment**

## **Instructions**

This assignment focuses on Object-Oriented Programming fundamentals. You'll create classes, define attributes and methods, and build GenAI-friendly examples.

**How to approach this:**
1. Read each task carefully
2. Write your code in a Python file (e.g., `day6_tasks.py`)
3. Create classes with proper structure
4. Test with multiple objects
5. For the mini project, create a separate file

**Important Notes:**
- Always use `self` for instance attributes and methods
- Use `__init__` to initialize objects
- Create meaningful method names
- Add docstrings to explain your classes and methods
- Test with multiple instances

---

## **Tasks**

### **Task 1: Basic Class Creation**

Create a `Book` class with:
1. `__init__` method that takes: title, author, year, pages
2. Attributes: title, author, year, pages, is_read (default False)
3. Methods:
   - `read()` - sets is_read to True
   - `get_info()` - returns formatted string with book details
   - `is_old()` - returns True if book is older than 20 years

Create 3 book objects and test all methods.

---

### **Task 2: Class with Calculations**

Create a `BankAccount` class with:
1. `__init__` method with: account_number, owner_name, initial_balance (default 0)
2. Attributes: account_number, owner_name, balance
3. Methods:
   - `deposit(amount)` - adds to balance
   - `withdraw(amount)` - subtracts from balance (check if sufficient funds)
   - `get_balance()` - returns current balance
   - `transfer(other_account, amount)` - transfers money to another account

Create 2 accounts, perform transactions, and display results.

---

### **Task 3: GenAI Prompt Template Class**

Create a `PromptTemplate` class with:
1. `__init__` method that takes a template string
2. Attributes: template, variables (dictionary)
3. Methods:
   - `set_variable(key, value)` - set a variable
   - `get_variable(key)` - get a variable value
   - `format()` - replace {variables} in template with values
   - `reset()` - clear all variables
   - `copy()` - create a copy of the template

Test with multiple templates and variables.

---

### **Task 4: LLM Configuration Class**

Create an `LLMConfig` class with:
1. `__init__` method with parameters: model, temperature, max_tokens
2. Attributes: model, temperature, max_tokens, api_key
3. Methods:
   - `set_api_key(key)` - set API key
   - `update_temperature(temp)` - update temperature (validate 0-2)
   - `update_max_tokens(tokens)` - update max tokens (validate > 0)
   - `get_config()` - return dictionary of all settings
   - `apply_preset(preset)` - apply "creative", "focused", or "balanced" preset

Create config objects and test all methods.

---

### **Task 5: Chat Message Class**

Create a `ChatMessage` class and `ChatHistory` class:

**ChatMessage:**
- Attributes: role, content, timestamp
- Methods: `to_dict()`, `__str__()`

**ChatHistory:**
- Attributes: messages (list)
- Methods:
  - `add_message(role, content)` - add message
  - `get_messages()` - return list of message dictionaries
  - `clear()` - clear all messages
  - `display()` - print all messages

Create a chat history, add messages, and display.

---

### **Task 6: Complete Application Class**

Create a `GenAIApplication` class that combines:
1. Attributes:
   - name
   - prompt_templates (list)
   - config (LLMConfig object)
   - chat_history (ChatHistory object)

2. Methods:
   - `create_prompt(template)` - create and store PromptTemplate
   - `list_prompts()` - display all prompts
   - `get_prompt(index)` - get prompt by index
   - `configure_llm(**settings)` - update LLM config
   - `add_chat_message(role, content)` - add to chat history
   - `get_summary()` - return summary of app state

Create an application, add prompts, configure LLM, add chat messages, and display summary.

---

## **Expected Output Section**

Each task should produce clear, readable output that demonstrates:
- Proper class definition with `__init__`
- Correct use of attributes and methods
- Multiple objects created from same class
- Methods working correctly
- GenAI-related classes functioning properly

Make sure your classes are well-structured and reusable.

---

## **Submission Checklist**

Before considering your Day 6 assignment complete, make sure:

- [ ] All 6 tasks are completed and working
- [ ] Classes are properly defined with `__init__`
- [ ] Attributes and methods are correctly implemented
- [ ] Multiple objects can be created from classes
- [ ] GenAI-related classes work correctly
- [ ] Code includes docstrings and comments
- [ ] Output is clean and readable
- [ ] No syntax errors
- [ ] You've tested with different inputs

**Good luck, and happy coding! 🚀**

