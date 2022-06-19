# Basic Git Workflow

# git init
  - init means initialize
  - sets up all the tools Git needs to track changes in code

  ```
    git init
  ```
  
# Basic Git Workflow
  - Git project can be thought of as having three parts:
    - Working directory: 
      - Make changes to files: additions, deletions, modifications
    - Staging area:
      - Files are ready for commit
    - Repository:
      - Changes are saved to a repository as a commit
 
## git status
  - Can check the status of the changes made in the working directory
  
  ```
    git status
  ```
  
## git add
  - In order for Git to start tracking files, they need to be added to the staging area
  
  ```
    git add filename
  ```
  
## git diff
  - Can check the differences between the working directory and the staging area with

  ```
    git diff filename
  ```
  
## git commit
  - A commit permanently stores changes from the staging area inside the repository

  ```
    git commit -m "Brief message in quotes, present tense, less than 50 characters"
  ```
  
## git log 
  - Often, you’ll need to refer back to an earlier version of a project
  - Commits are stored chronologically in the repository

  ``` 
    git log
  ```
  
  - A 40-character code (SHA) that uniquely identifies the commit (appears in orange text)
  - The commit author
  - The date and time of commit
  - Commit message

