# Language for Goals (LFG) Syntax Specification

## 1. Introduction

The Language for Goals (LFG) is a syntax designed to efficiently represent goals, tasks, and subtasks in a human-readable format. This document provides a comprehensive description of the LFG syntax and its features, which include integration with git and directory structures, use of special formatting blocks, compatibility with various data formats, and task status and priority indicators.

## 2. LFG Syntax

### 2.1 Goals and Tasks

Goals are represented by a semicolon (;) followed by a series of subcategories separated by greater-than signs (>). The syntax is as follows:

`;[Optional: Maslow's Hierarchy Level]>[Subcategory]>[Subcategory]>[Task][...!$]`

Example:

`;Esteem>Networking>Write Weekly Articles>The Article about the Syntax for Productivity...`

### 2.2 Task Status Indicators

LFG provides a set of symbols to indicate the status of a task:
- `;` (semicolon): Represents an uncompleted task or a to-do item.
- `!` (exclamation mark): Represents a completed task, symbolizing a triumphant "Yay!"
- `...` (ellipsis): Represents a task in progress.

### 2.3 Task Priority Indicators

LFG also provides a way to assign priority or value to each task using the `$` (dollar sign) symbol:
- `$`: Low priority or value.
- `$$`: Medium priority or value.
- `$$$`: High priority or value.

### 2.4 Directory Structure and File Types

The root folder for goals is named `_goals`. Within this folder, `.lfg` and `.md` files with recognizable single-line code containing the LFG syntax or code blocks with  ```lfg blocks can be used to store goals and tasks.

Folders inside `_goals` may further define subgoals, or files.  Since goals are more like namespaces (with `>` used as a delimiter) than folders, they can appear in any file in the structure.  A file can contain one or more goals.

### 2.5 Task Details and Data Formats

In an LFG file or line of goal syntax like `;Physiological>Hydration>Drink Water...`, braces (`{}`) can be added to include further task details and data in Markdown (Extended Syntax). These details can be stored in various data formats, such as JSON, YAML, XML, TOML, CSV, and INI, using the following code blocks:

````
   ```json
   ```yaml
   ```xml
   ```toml
   ```csv
   ```ini
````


````
   ```lfg
   ;Physiological>Hydration>Drink Water...{
      #Why I should drink water_
      - Because the AI came up with this goal for me
      - Because we're made of water

      #When I should drink water
      `0 */2 * * *`

      #how I should drink water
      ```
         tip, tip, tip,
      ```

     ```json {
     "duration": "4 seconds",
     "supplies": "Water bottle"
     }```
   }
   ```
````

### 2.6 Collaboration and Version Control
Goals can be shared via git as you would any other repository. Users+AI+(Tesla Robots?) can suggest modifications, collaborate, complete tasks, additionally-subtask, detail, simplify, clarify and more.

### 2.7 Integration with Pull Requests and Merge Requests
The LFG syntax should be designed to work seamlessly with Pull Requests (PRs) and Merge Requests (MRs) in popular version control systems like Git. This will enable users to easily manage tasksand goals as part of their development workflow.

#### 2.7.1 Scanning Commit Comments for Tasks and Completions
The LFG system should automatically scan commit comments for tasks and completions, allowing users to track their progress and make updates directly from their commit messages. This will provide a more streamlined experience and help keep tasks and goals up to date.

To achieve this, the LFG system should:
- Look for LFG syntax in commit comments, identifying tasks, completions, and other relevant information.
- Update the relevant tasks and goals based on the information extracted from the commit comments.
- Provide users with an overview of their progress and any changes made to their tasks and goals as a result of the commit comments.

This integration with PRs and MRs will help make the LFG syntax even more useful and versatile for users, enabling them to manage their tasks and goals as part of their existing development workflows.

## Conclusion

The LFG syntax provides an efficient and human-readable way to represent and manage goals and tasks. By leveraging git, directory structures, and various data formats, users can collaborate and share goals, making the LFG syntax a powerful tool for personal and professional productivity.

This document serves as an RFC-style description of the LFG syntax, covering its essential features and functionality. Further development and refinement of the syntax will be guided by user feedback and real-world application.
```
