# LFG Syntax RFC (Language for Goals)

## 1. Abstract

The Language for Goals (LFG) is a syntax designed to efficiently represent goals, tasks, and subtasks in a human-readable format. This document provides a comprehensive description of the LFG syntax and its features, which include task hierarchies, priorities, deadlines, tags, notes, Markdown formatting, integration with git and directory structures, compatibility with various data formats, and task status indicators.

## 2. LFG Syntax

### 2.2 Task Creation
- `[ ]` - Create an empty task
- `[x]` - Create a completed task
- `[~]` - Create a task in progress

### 2.3 Task Priorities
- `$$$` - High priority
- `$$` - Medium priority
- `$` - Low priority

### 2.4 Task Deadlines
- `(2023-05-15)` - Set a deadline using YYYY-MM-DD format

### 2.5 Task Categories and Nesting
- `;Category>Sub>Sub` - Create categories and subcategories (preferably themselves actually worded as Goals/Large tasks) using greater-than symbols for namespacing
- `>` - Use a greater-than symbol to create nested tasks and subtasks within categories, following the same namespacing pattern

### 2.6 Task Notes
- `{Note}` - Add a note to a task using braces; supports Markdown formatting inside braces

### 2.7 Task Tags
- `#tag` - Add a tag to a task using the hashtag symbol

## 3. Directory Structure and File Types

The root folder for goals is named `_goals`. Within this folder, `.lfg` and `.md` files with recognizable single-line code containing the LFG syntax or code blocks with ```lfg blocks can be used to store goals and tasks.

Folders inside `_goals` may further define subgoals or files. Since goals are more like namespaces (with `>` used as a delimiter) than folders, they can appear in any file in the structure. A file can contain one or more goals.

## 4. Notes, Task Details, and Extended Data

In an LFG file or line of goal syntax like `;Physiological>Hydration> [~] Drink Water`, braces (`{}`) can be added to include further {notes} or task details and data in Markdown (Extended Syntax). These details can be stored in various data formats, such as JSON, YAML, XML, TOML, CSV, and INI, using the following code blocks:

````
   ```json
   ```yaml
   ```xml
   ```toml
   ```csv
   ```ini
   ```lfg
````

Example:
````
;Physiological>Hydration> [~] Drink Water {
   #Why I should drink water
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

````

## 5. Collaboration and Version Control

Goals can be shared via git as you would any other repository. Users+AI+(Tesla Robots?) can suggest modifications, collaborate, complete tasks, additionally-subtask, detail, simplify, clarify and more.

The LFG syntax should be designed to work seamlessly with Pull Requests (PRs) and Merge Requests (MRs) in popular version control systems like Git. This will enable users to easily manage tasks and goals as part of their development workflow.

### 5.1 Scanning Commit Comments for Tasks and Completions

The LFG system should automatically scan commit comments for tasks and completions, allowing users to track their progress and make updates directly from their commit messages. This will provide a more streamlined experience and help keep tasks and goals up to date.

To achieve this, the LFG system should:

1. Look for LFG syntax in commit comments, identifying tasks, completions, and other relevant information.
2. Update the relevant tasks and goals based on the information extracted from the commit comments.
3. Provide users with an overview of their progress and any changes made to their tasks and goals as a result of the commit comments.

This integration with PRs and MRs will help make the LFG syntax even more useful and versatile for users, enabling them to manage their tasks and goals as part of their existing development workflows.

## 6. More Examples

```

;Tasks>Project>Design

[ ] Complete the LFG proposal (2023-05-13) $$$ #proposal
> [~] Review the LFG syntax $$ #review
> > [ ] Update the example with new syntax $ #update
> > [x] Test nesting functionality $ #test
[x] Share LFG idea with the team (2023-05-11) $$ #share

;Meetings>Team

[ ] Prepare slides for LFG presentation (2023-05-14) $$$ #presentation {**Include** examples and *benefits*}
[x] Schedule a meeting with the design team (2023-05-10) $$ #meeting {Discussed LFG integration with existing tools}

```

## 7. Conclusion

The LFG syntax provides an efficient and human-readable way to represent and manage goals and tasks. By leveraging git, directory structures, and various data formats, users can collaborate and share goals, making the LFG syntax a powerful tool for personal and professional productivity.

This document serves as an RFC-style description of the LFG syntax, covering its essential features and functionality. Further development and refinement of the syntax will be guided by user feedback and real-world application.
