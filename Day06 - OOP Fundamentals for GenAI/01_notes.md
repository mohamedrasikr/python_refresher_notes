# **Day 6 — OOP Fundamentals for GenAI**

## **Learning Objectives**

| # | Learning Objective | Description |
|---|-------------------|-------------|
| 1 | What is a Class? | Understand classes as blueprints for creating objects |
| 2 | Objects, Attributes, and Methods | Create objects with data (attributes) and behavior (methods) |
| 3 | Constructors (`__init__`) | Initialize objects with the constructor method |
| 4 | GenAI Examples | Apply OOP concepts to GenAI use cases like prompt templates |

---

## **1. Introduction**

Today we're learning Object-Oriented Programming (OOP) fundamentals. OOP helps you organize code by grouping related data and functions together. In GenAI work, you'll use classes to create prompt templates, manage API configurations, and structure your applications.

We'll cover classes as blueprints, objects as instances, attributes for data storage, methods for behavior, and constructors for initialization. These concepts form the foundation for building more complex applications.

---

## **2. Deep-Dive Explanation**

### **What is a Class?**

A class is a blueprint for creating objects. It defines what attributes (data) and methods (functions) the objects will have. Think of a class as a cookie cutter - you use it to create many cookies (objects) that all have the same shape.

```python
class Dog:
    pass

# Create objects (instances) from the class
my_dog = Dog()
your_dog = Dog()
```

**Class vs Object:**
- **Class**: The blueprint (e.g., "Dog")
- **Object/Instance**: A specific item created from the class (e.g., "my_dog")

### **Objects, Attributes, and Methods**

**Attributes** are variables that belong to an object. They store data about the object.

```python
class Dog:
    pass

my_dog = Dog()
my_dog.name = "Buddy"      # Attribute
my_dog.age = 3             # Attribute
my_dog.breed = "Golden Retriever"  # Attribute

print(my_dog.name)  # Output: Buddy
```

**Methods** are functions that belong to an object. They define what the object can do.

```python
class Dog:
    def bark(self):  # Method
        return "Woof!"
    
    def get_info(self):  # Method
        return f"{self.name} is {self.age} years old"

my_dog = Dog()
my_dog.name = "Buddy"
my_dog.age = 3

print(my_dog.bark())      # Output: Woof!
print(my_dog.get_info())  # Output: Buddy is 3 years old
```

**The `self` parameter:**
- `self` refers to the instance (object) calling the method
- It's automatically passed when you call a method
- You use `self` to access attributes and other methods

### **Constructors (`__init__`)**

The `__init__` method is a special method called when you create an object. It's used to initialize attributes.

```python
class Dog:
    def __init__(self, name, age, breed):
        self.name = name
        self.age = age
        self.breed = breed
        print(f"{name} has been created!")

# Create objects with initial values
my_dog = Dog("Buddy", 3, "Golden Retriever")
your_dog = Dog("Max", 5, "German Shepherd")

print(my_dog.name)   # Output: Buddy
print(your_dog.age)  # Output: 5
```

**Default parameters:**
```python
class Dog:
    def __init__(self, name, age=1, breed="Unknown"):
        self.name = name
        self.age = age
        self.breed = breed

# Can omit optional parameters
dog1 = Dog("Buddy")                    # Uses defaults
dog2 = Dog("Max", 5)                   # age=5, breed="Unknown"
dog3 = Dog("Charlie", 2, "Labrador")  # All specified
```

**Multiple methods:**
```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age
        self.hungry = True
    
    def bark(self):
        return "Woof!"
    
    def eat(self):
        self.hungry = False
        return f"{self.name} is eating"
    
    def get_info(self):
        status = "hungry" if self.hungry else "full"
        return f"{self.name} is {self.age} years old and {status}"

my_dog = Dog("Buddy", 3)
print(my_dog.get_info())  # Buddy is 3 years old and hungry
print(my_dog.eat())       # Buddy is eating
print(my_dog.get_info())  # Buddy is 3 years old and full
```

### **GenAI-Friendly Examples**

**Prompt Template Class:**
```python
class PromptTemplate:
    def __init__(self, template, variables=None):
        self.template = template
        self.variables = variables or {}
    
    def add_variable(self, key, value):
        self.variables[key] = value
    
    def format(self):
        """Format the prompt with current variables."""
        result = self.template
        for key, value in self.variables.items():
            result = result.replace(f"{{{key}}}", str(value))
        return result
    
    def update_template(self, new_template):
        self.template = new_template

# Usage
prompt = PromptTemplate(
    "Write a {genre} story about {character} in {setting}."
)
prompt.add_variable("genre", "sci-fi")
prompt.add_variable("character", "Alice")
prompt.add_variable("setting", "Mars")

formatted = prompt.format()
print(formatted)
# Output: Write a sci-fi story about Alice in Mars.
```

**LLM Configuration Class:**
```python
class LLMConfig:
    def __init__(self, model="gpt-3.5-turbo", temperature=0.7, max_tokens=1000):
        self.model = model
        self.temperature = temperature
        self.max_tokens = max_tokens
        self.api_key = None
    
    def set_api_key(self, key):
        self.api_key = key
    
    def update_temperature(self, temp):
        if 0 <= temp <= 2:
            self.temperature = temp
        else:
            print("Temperature must be between 0 and 2")
    
    def get_config(self):
        return {
            "model": self.model,
            "temperature": self.temperature,
            "max_tokens": self.max_tokens
        }
    
    def __str__(self):
        return f"LLMConfig(model={self.model}, temp={self.temperature})"

# Usage
config = LLMConfig(temperature=0.9, max_tokens=2000)
config.set_api_key("sk-...")
print(config.get_config())
print(config)
```

**Message Class for Chat:**
```python
class ChatMessage:
    def __init__(self, role, content):
        self.role = role  # "user", "assistant", "system"
        self.content = content
        self.timestamp = None
    
    def to_dict(self):
        return {
            "role": self.role,
            "content": self.content
        }
    
    def __str__(self):
        return f"[{self.role}]: {self.content}"

class ChatHistory:
    def __init__(self):
        self.messages = []
    
    def add_message(self, role, content):
        message = ChatMessage(role, content)
        self.messages.append(message)
    
    def get_messages(self):
        return [msg.to_dict() for msg in self.messages]
    
    def display(self):
        for msg in self.messages:
            print(msg)

# Usage
chat = ChatHistory()
chat.add_message("user", "Hello, how are you?")
chat.add_message("assistant", "I'm doing well, thank you!")
chat.display()
```

---

## **3. Instructor Examples**

### **Example 1: Basic Class with Attributes and Methods**

```python
class Student:
    def __init__(self, name, student_id, age):
        self.name = name
        self.student_id = student_id
        self.age = age
        self.grades = []
    
    def add_grade(self, grade):
        """Add a grade to the student's record."""
        if 0 <= grade <= 100:
            self.grades.append(grade)
        else:
            print("Grade must be between 0 and 100")
    
    def calculate_average(self):
        """Calculate average grade."""
        if self.grades:
            return sum(self.grades) / len(self.grades)
        return 0
    
    def get_info(self):
        """Get student information."""
        avg = self.calculate_average()
        return f"{self.name} (ID: {self.student_id}) - Average: {avg:.2f}"

# Usage
student1 = Student("Alice", "S001", 20)
student1.add_grade(85)
student1.add_grade(90)
student1.add_grade(88)

print(student1.get_info())
print(f"Grades: {student1.grades}")
```

**Output:**
```
Alice (ID: S001) - Average: 87.67
Grades: [85, 90, 88]
```

### **Example 2: GenAI Prompt Template**

```python
class PromptTemplate:
    def __init__(self, base_template):
        self.base_template = base_template
        self.variables = {}
    
    def set_variable(self, key, value):
        """Set a variable for the template."""
        self.variables[key] = value
    
    def format(self):
        """Format the template with current variables."""
        result = self.base_template
        for key, value in self.variables.items():
            placeholder = "{" + key + "}"
            result = result.replace(placeholder, str(value))
        return result
    
    def reset(self):
        """Clear all variables."""
        self.variables = {}

# Usage
template = PromptTemplate(
    "Generate a {type} about {topic} for {audience}."
)

template.set_variable("type", "blog post")
template.set_variable("topic", "Python programming")
template.set_variable("audience", "beginners")

prompt = template.format()
print(prompt)
```

**Output:**
```
Generate a blog post about Python programming for beginners.
```

### **Example 3: LLM Settings Manager**

```python
class LLMSettings:
    def __init__(self, model="gpt-3.5-turbo"):
        self.model = model
        self.temperature = 0.7
        self.max_tokens = 1000
        self.top_p = 1.0
        self.frequency_penalty = 0.0
    
    def update_temperature(self, temp):
        """Update temperature setting."""
        if 0 <= temp <= 2:
            self.temperature = temp
            return True
        return False
    
    def get_settings_dict(self):
        """Get all settings as a dictionary."""
        return {
            "model": self.model,
            "temperature": self.temperature,
            "max_tokens": self.max_tokens,
            "top_p": self.top_p,
            "frequency_penalty": self.frequency_penalty
        }
    
    def apply_preset(self, preset_name):
        """Apply a preset configuration."""
        presets = {
            "creative": {"temperature": 0.9, "top_p": 0.9},
            "focused": {"temperature": 0.3, "top_p": 0.5},
            "balanced": {"temperature": 0.7, "top_p": 1.0}
        }
        if preset_name in presets:
            settings = presets[preset_name]
            self.temperature = settings["temperature"]
            self.top_p = settings["top_p"]
            return True
        return False

# Usage
llm = LLMSettings()
print("Default:", llm.get_settings_dict())

llm.apply_preset("creative")
print("Creative:", llm.get_settings_dict())
```

**Output:**
```
Default: {'model': 'gpt-3.5-turbo', 'temperature': 0.7, 'max_tokens': 1000, 'top_p': 1.0, 'frequency_penalty': 0.0}
Creative: {'model': 'gpt-3.5-turbo', 'temperature': 0.9, 'max_tokens': 1000, 'top_p': 0.9, 'frequency_penalty': 0.0}
```

### **Example 4: Complete GenAI Application Class**

```python
class GenAIApp:
    def __init__(self, name):
        self.name = name
        self.prompts = []
        self.config = LLMSettings()
    
    def create_prompt(self, template):
        """Create and store a prompt template."""
        prompt = PromptTemplate(template)
        self.prompts.append(prompt)
        return prompt
    
    def list_prompts(self):
        """List all stored prompts."""
        for i, prompt in enumerate(self.prompts, 1):
            print(f"{i}. {prompt.base_template}")
    
    def get_config(self):
        """Get current LLM configuration."""
        return self.config.get_settings_dict()

# Usage
app = GenAIApp("My GenAI App")
app.config.apply_preset("creative")

prompt1 = app.create_prompt("Write a story about {character}")
prompt1.set_variable("character", "a robot")
print(prompt1.format())

app.list_prompts()
print("\nConfig:", app.get_config())
```

---

## **4. Summary / Key Takeaways**

- **Classes** are blueprints for creating objects
- **Objects** are instances created from a class
- **Attributes** store data about an object (e.g., `self.name`)
- **Methods** are functions that belong to an object (e.g., `def method(self):`)
- **`__init__`** is the constructor method that runs when an object is created
- **`self`** refers to the instance and is used to access attributes and methods
- Classes help organize code by grouping related data and functions
- OOP makes code reusable and easier to maintain
- GenAI applications benefit from classes for prompt templates, configurations, and data structures
- You can create multiple objects from the same class, each with its own data

---

