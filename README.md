# ToDo API
Simple To-Do GraphQL API created using Python, Ariadne and Flask.

I followed the approach described in this post: https://www.twilio.com/en-us/blog/graphql-api-python-flask-ariadne

# Installation
- Create Python Environment
  ```zsg
  python3 -m venv venv # this will create a new virtual environment called "venv"
  ```
- Activate Python Virtual Environment
  ```zsh
  source ./venv/bin/activate
  ```
- Install Dependencies
  ```zsh
  pip install -r requirements.txt
  ```
- Run Project
  ```zsh
  flask --app main.py run
  ```

# Example GraphQL Queries
```graphql
  query fetchAllTodos {
    todos {
      success
      errors
      todos {
        description
        completed
        dueDate
        id
      }
    }
  }
  
  query fetchTodo {
    todo(todoId: "1") {
      success
      errors
      todo {
        id
        completed
        description
        dueDate
      }
    }
  }
  
  mutation newTodo {
    createTodo(description: "Test ToDo", dueDate: "24-10-2024") {
      success
      errors
      todo {
        id
        completed
        description
      }
    }
  }
  
  mutation markDone {
    markDone(todoId: "1") {
      success
      errors
      todo {
        id
        completed
        description
        dueDate
      }
    }
  }
  
  mutation deleteTodo {
    deleteTodo(todoId: "1") {
      success
      errors
    }
  }
  
  mutation updateDueDate {
    updateDueDate(todoId: "1", newDate: "25-10-2024") {
      success
      errors
    }
  }
```
