# To-Do List CLI Application (Golang)

## Overview
This project is a command-line To-Do List application written in **Go**. It allows users to **add, list, mark as done, and remove tasks**, persisting data using the local file system. The application presents tasks in a **tabular format** for better readability. The project is designed to teach file I/O operations, working with structured data (JSON), and formatting terminal output.

## Features
- **Add Task**: Add a new task to the list.
- **List Tasks**: Display tasks in a formatted table.
- **Mark Task as Done**: Update the status of a task.
- **Remove Task**: Delete a task from the list.
- **Persistent Storage**: Save and load tasks using a local JSON file.

## Technical Design

### Data Structure
Tasks are stored as JSON objects with the following structure:
```json
[
  {
    "id": 1,
    "description": "Write project README",
    "done": false
    "time_added": datetime
    "due_date": datetime
  },
  {
    "id": 2,
    "description": "Learn file operations in Go",
    "done": true
    "time_added": datetime
    "due_date": datetime
  }
]
```

### File Handling
- Tasks will be stored in `tasks.json`.
- The application will **read the file at startup** and **write to it upon modifications**.

### Command-Line Interface (CLI)
Commands will be structured as follows:
```sh
./todo add "Write project README"      # Adds a task
./todo list                             # Lists tasks
./todo done 1                           # Marks task with ID 1 as done
./todo remove 2                         # Removes task with ID 2
```

### External Libraries
- **Encoding/Decoding JSON**: `encoding/json`
- **File I/O**: `os`, `ioutil`
- **Tabular Output**: `github.com/olekukonko/tablewriter`

## Implementation Plan
1. **Initialize Go Module** (`go mod init todo`)
2. **Define Task Struct** (with ID, description, and done status)
3. **Implement File I/O Functions**
   - Read from `tasks.json`
   - Write to `tasks.json`
4. **Implement CLI Commands**
   - Parsing user input
   - Handling commands
5. **Format Output as Table**
6. **Error Handling & Edge Cases**
   - Handle empty lists
   - Prevent duplicate IDs
   - Validate user inputs
7. **Testing**
   - Unit tests for file handling and CLI commands
8. **Enhancements** (Optional)
   - Implement categories or priorities
   - Use a database instead of JSON for larger datasets
   - Add a TUI (Text User Interface) using `tview`

## Expected Learning Outcomes
- **File handling**: Read/write operations with JSON in Go.
- **Data persistence**: Storing structured data locally.
- **Command-line interaction**: Parsing and handling user input.
- **Formatting data**: Presenting information in a readable format.
- **Structuring a Go project**: Organizing code for maintainability.

## Future Improvements
- **Support for due dates and reminders**
- **Sync tasks across devices using cloud storage**
- **GUI version using a web framework like Gin**

---
### Getting Started
#### Prerequisites
- Install **Go** (latest version recommended)

#### Installation
```sh
git clone https://github.com/yourusername/todo-cli.git
cd todo-cli
go mod init todo-cli
go build -o todo
./todo --help
```

#### Running the Application
```sh
./todo add "Finish Go project"
./todo list
```

---
This project will help reinforce fundamental Go skills while building a **useful, real-world application**!

