# 🧭 The Learning Compass: Multi-Agent Curriculum Generator

**A sequential multi-agent AI system built with Google's Agent Development Kit (ADK) and Gemini 2.5.**

## 📋 Project Overview
The Learning Compass is an AI-powered educational tool that orchestrates three specialized agents to generate high-quality, structured learning materials. Unlike a standard chatbot, this system separates concerns (Planning, Content, Evaluation) to ensure structural integrity and hallucination reduction.

This project was built as a Capstone for the **Google x Kaggle 5-Day AI Agents Intensive**.

## 🧩 Architecture Diagram
![The Learning Compass Architecture](Architecture_Diagram.png)

## 🛠️ Technical Stack
* **Framework:** Google Agent Development Kit (`google-adk`)
* **Model:** Gemini 2.5 Flash Lite
* **Concepts Applied:** Tool Use, Multi-Agent Orchestration, LLM-as-a-Judge, Robust Error Handling.

## 🚀 How to Run
1.  Clone the repository:
    ```bash
    git clone https://github.com/abhictrl/learning-compass-agent.git
    ```
2.  Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```
3.  Set up your API Key:
    * Get a key from [Google AI Studio](https://aistudio.google.com/).
    * Set it in your environment variables as `GOOGLE_API_KEY`.
4.  Run the notebook in `notebooks/learning_compass_agent.ipynb`.

## 📸 Example Output

Here is a complete execution run generating a **Day 1 Lesson for Data Structures and Algorithms (Intermediate)**.

<details>
<summary><strong>Click to expand the full execution log</strong></summary>

```text
🏁 Starting Learning Compass for: Data Structures and Algorithms (Intermediate)

--- 🤖 PLANNER AGENT WORKING ---

### Created new session: debug_session_id

User > Create a syllabus for 'Data Structures and Algorithms' at Intermediate level.

PlannerAgent > In order to create a syllabus for 'Data Structures and Algorithms' at an 'Intermediate' level, I need to know what topics you'd like to cover. The template provides a structure, but I need the specific content. Can you please provide the topics for each of the 3 days?

--- 🤖 CONTENT AGENT WORKING ---

User > Write the 'Day 1' lesson for this syllabus.

ContentAgent > ## Day 1: Introduction to Data Structures & Algorithmic Thinking

Welcome to Intermediate Data Structures and Algorithms! Today, we'll lay the groundwork for our journey into efficient data organization and problem-solving.

**What are Data Structures?** Think of them as specialized containers for organizing and storing data. The choice of data structure dramatically impacts how efficiently we can access, modify, and process information. We'll explore fundamental structures like **arrays** and **linked lists**, understanding their strengths, weaknesses, and common use cases.

**What is Algorithmic Thinking?** This is the art of breaking down complex problems into a series of well-defined steps, or algorithms. We'll focus on developing your ability to design, analyze, and implement these step-by-step solutions.

**Key Concepts:**

* **Abstract Data Types (ADTs):** A conceptual blueprint for data structures, focusing on operations rather than implementation details.
* **Time and Space Complexity (Big O Notation):** We'll introduce the crucial concept of analyzing algorithm efficiency. How much time (time complexity) and memory (space complexity) does an algorithm consume as the input size grows?

**Practical Example: Array vs. Linked List Insertion**

Imagine you have a list of items and need to insert a new item at the beginning.

* **Array:** Inserting at the beginning requires shifting all existing elements one position to the right. This can be slow for large arrays.
* **Linked List:** Inserting at the beginning is incredibly efficient. You just create a new node and point it to the original head.

**Code Snippet (Conceptual Python):**

```python
# Illustrative, not a full implementation

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def insert_at_beginning(self, new_data):
        new_node = Node(new_data)
        new_node.next = self.head
        self.head = new_node

# Example Usage:
my_list = LinkedList()
my_list.insert_at_beginning(10)
my_list.insert_at_beginning(5)
# Now, 5 is at the head.

Today is about building intuition and understanding the "why" behind choosing specific data structures and designing efficient algorithms. Get ready to think computationally!

--- 🤖 EVALUATOR AGENT WORKING ---

User > Evaluate this lesson content.

EvaluatorAgent >

{
  "score": 4,
  "reasoning": "The lesson provides a solid introduction to the core concepts of data structures and algorithmic thinking. It clearly defines what data structures and algorithmic thinking are, introduces important related concepts like ADTs and Big O notation, and illustrates a key difference between arrays and linked lists with a practical example and conceptual code. The content is well-organized and suitable for an introductory lesson.",
  "status": "PASS"
}
