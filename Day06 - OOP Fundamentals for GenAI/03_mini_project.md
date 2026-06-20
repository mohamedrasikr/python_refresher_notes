# **Day 6 — Mini Project**

## **Project Overview**

Build a `PromptTemplate` class system for GenAI that allows creating, managing, and formatting prompt templates. This project demonstrates OOP principles while creating a practical tool for GenAI work.

---

## **Project Requirements**

Your program must:

1. **Create a `PromptTemplate` class** with:
   - Template string with placeholders
   - Variable management
   - Formatting capabilities

2. **Create a `PromptManager` class** that:
   - Stores multiple prompt templates
   - Allows creating, viewing, and deleting templates
   - Provides search functionality

3. **Create an `LLMConfig` class** for:
   - Model settings (temperature, max_tokens, etc.)
   - Preset configurations
   - Settings validation

4. **Main menu** with options:
   - Create new prompt template
   - List all templates
   - Format a template
   - Search templates
   - Configure LLM settings
   - View configuration
   - Exit

5. **Features**:
   - Save templates with names/descriptions
   - Format templates with variables
   - Apply LLM presets
   - Display formatted prompts

---

## **Step-by-Step Instructions**

1. **Set up your file**
   - Create `prompt_template_system.py`
   - Add comment header

2. **Create PromptTemplate class**
   - `__init__(self, name, template, description="")`
   - Attributes: name, template, description, variables
   - Methods:
     - `set_variable(key, value)`
     - `get_variable(key)`
     - `format()` - replace {variables}
     - `get_info()` - return template info
     - `__str__()` - string representation

3. **Create PromptManager class**
   - `__init__(self)`
   - Attributes: templates (list)
   - Methods:
     - `add_template(template)` - add PromptTemplate
     - `get_template(name)` - find by name
     - `list_templates()` - display all
     - `search_templates(query)` - search by name/description
     - `remove_template(name)` - delete template
     - `count()` - return number of templates

4. **Create LLMConfig class**
   - `__init__(self, model="gpt-3.5-turbo")`
   - Attributes: model, temperature, max_tokens, top_p
   - Methods:
     - `update_temperature(temp)` - validate 0-2
     - `update_max_tokens(tokens)` - validate > 0
     - `apply_preset(preset)` - creative/focused/balanced
     - `get_config()` - return dict
     - `display()` - show current settings

5. **Create main application**
   - Initialize PromptManager and LLMConfig
   - Create menu loop
   - Implement each menu option
   - Use functions to organize code

6. **Implement menu options**
   - Create template: Get name, template, description
   - List templates: Show all with numbers
   - Format template: Select template, set variables, format
   - Search: Find templates by keyword
   - Configure LLM: Update settings or apply preset
   - View config: Display current LLM settings

7. **Add error handling**
   - Validate template names (unique)
   - Handle missing templates
   - Validate variable inputs
   - Handle configuration errors

8. **Test thoroughly**
   - Create multiple templates
   - Test formatting with variables
   - Test search functionality
   - Test LLM configuration
   - Test all error cases

---

## **Example Interaction / Output**

```
╔══════════════════════════════════════╗
║   Prompt Template System            ║
╚══════════════════════════════════════╝

Menu:
1. Create new prompt template
2. List all templates
3. Format a template
4. Search templates
5. Configure LLM settings
6. View LLM configuration
7. Exit

Enter your choice: 1

Enter template name: Blog Post Generator
Enter template: Write a {length} {type} blog post about {topic} for {audience}.
Enter description: Generates blog post prompts

Template 'Blog Post Generator' created!

Enter your choice: 1

Enter template name: Story Creator
Enter template: Create a {genre} story featuring {character} in {setting}.
Enter description: Story generation template

Template 'Story Creator' created!

Enter your choice: 2

═══════════════════════════════════════
All Templates:
═══════════════════════════════════════
1. Blog Post Generator
   Description: Generates blog post prompts
   Template: Write a {length} {type} blog post about {topic} for {audience}.

2. Story Creator
   Description: Story generation template
   Template: Create a {genre} story featuring {character} in {setting}.
═══════════════════════════════════════

Enter your choice: 3

Select template (enter name): Blog Post Generator

Set variables:
Enter 'length': 1000-word
Enter 'type': informative
Enter 'topic': Python programming
Enter 'audience': beginners

Formatted Prompt:
Write a 1000-word informative blog post about Python programming for beginners.

Enter your choice: 5

LLM Configuration:
1. Update temperature
2. Update max tokens
3. Apply preset (creative/focused/balanced)
4. Back to main menu

Enter choice: 3

Select preset (creative/focused/balanced): creative

Applied 'creative' preset:
  Temperature: 0.9
  Top P: 0.9

Enter your choice: 6

Current LLM Configuration:
Model: gpt-3.5-turbo
Temperature: 0.9
Max Tokens: 1000
Top P: 0.9

Enter your choice: 7
Goodbye!
```

**Note:** Your output format can vary, but it should be clear and organized.

---

## **Bonus Challenges (Optional)**

1. **Save/Load**: Save templates to JSON file and load on startup
2. **Template categories**: Organize templates by category
3. **Variable validation**: Validate variable types and ranges
4. **Template editing**: Modify existing templates
5. **Export prompts**: Export formatted prompts to text file
6. **Template statistics**: Track usage of each template
7. **Batch formatting**: Format multiple templates at once
8. **Template inheritance**: Create templates based on others

---

## **Tips & Hints**

- **PromptTemplate structure:**
  ```python
  class PromptTemplate:
      def __init__(self, name, template, description=""):
          self.name = name
          self.template = template
          self.description = description
          self.variables = {}
  ```

- **Formatting with variables:**
  ```python
  def format(self):
      result = self.template
      for key, value in self.variables.items():
          result = result.replace(f"{{{key}}}", str(value))
      return result
  ```

- **Finding template by name:**
  ```python
  def get_template(self, name):
      for template in self.templates:
          if template.name.lower() == name.lower():
              return template
      return None
  ```

- **LLM preset structure:**
  ```python
  presets = {
      "creative": {"temperature": 0.9, "top_p": 0.9},
      "focused": {"temperature": 0.3, "top_p": 0.5},
      "balanced": {"temperature": 0.7, "top_p": 1.0}
  }
  ```

- **Menu organization**: Use functions for each menu option
- **Error handling**: Check if template exists before operations
- **Input validation**: Validate temperature (0-2), tokens (>0)
- **String formatting**: Use f-strings for clean output

---

**Good luck building your prompt template system!**

