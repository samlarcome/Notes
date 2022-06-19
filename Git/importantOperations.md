# Important Git Operations

## head commit
  - In Git, the commit you are currently on is known as the HEAD commit
  - Usually the most recent commit is the head commit
  
  ```
    git show HEAD
  ```
  - Shows everything ```git log``` shows plus the file changes that were committed


## git checkout
  
  ```
    git checkout HEAD filename
  ```
  - Restores the file in your working directory to look exactly as it did when you last made a commit
