`git stash` is a powerful command in Git that allows you to temporarily save (stash) changes you have made to your working directory, so you can work on something else and then reapply those changes later. This is particularly useful when you need to switch branches but don't want to commit half-done work.

### Key Concepts and Commands

1. **Stashing Changes**
   - `git stash`: Saves your current changes and reverts your working directory to the state of the last commit.
     ```sh
     git stash
     ```
   - `git stash save "description"`: Adds a description to your stash.
     ```sh
     git stash save "WIP: fixing bug #42"
     ```

2. **Viewing Stashes**
   - `git stash list`: Lists all the stashes you have saved.
     ```sh
     git stash list
     ```
     Example output:
     ```plaintext
     stash@{0}: WIP on main: 4a1e2bc Fix user login bug
     stash@{1}: WIP on feature-branch: 9b3c4de Add new feature
     ```

3. **Applying Stashes**
   - `git stash apply`: Applies the most recent stash without removing it from the stash list.
     ```sh
     git stash apply
     ```
   - `git stash apply stash@{n}`: Applies a specific stash from the stash list.
     ```sh
     git stash apply stash@{1}
     ```

4. **Dropping Stashes**
   - `git stash drop`: Removes the most recent stash from the stash list.
     ```sh
     git stash drop
     ```
   - `git stash drop stash@{n}`: Removes a specific stash from the stash list.
     ```sh
     git stash drop stash@{1}
     ```

5. **Popping Stashes**
   - `git stash pop`: Applies the most recent stash and removes it from the stash list.
     ```sh
     git stash pop
     ```
   - `git stash pop stash@{n}`: Applies a specific stash and removes it from the stash list.
     ```sh
     git stash pop stash@{1}
     ```

6. **Stashing Untracked and Ignored Files**
   - `git stash -u` or `git stash --include-untracked`: Stashes untracked files as well.
     ```sh
     git stash -u
     ```
   - `git stash -a` or `git stash --all`: Stashes all files, including untracked and ignored files.
     ```sh
     git stash -a
     ```

7. **Creating a Branch from a Stash**
   - `git stash branch <branch-name>`: Creates a new branch from a stash and applies the stash to it.
     ```sh
     git stash branch new-feature-branch
     ```

### Practical Examples

1. **Stash Your Changes**
   ```sh
   git stash
   ```

2. **List All Stashes**
   ```sh
   git stash list
   ```

3. **Apply the Most Recent Stash**
   ```sh
   git stash apply
   ```

4. **Apply a Specific Stash**
   ```sh
   git stash apply stash@{1}
   ```

5. **Pop the Most Recent Stash**
   ```sh
   git stash pop
   ```

6. **Drop a Specific Stash**
   ```sh
   git stash drop stash@{1}
   ```

7. **Stash Untracked Files**
   ```sh
   git stash -u
   ```

8. **Create a Branch from a Stash**
   ```sh
   git stash branch new-feature-branch
   ```

### Example Workflow Using Git Stash

Imagine you are working on a feature and suddenly need to switch to another branch to fix a critical bug.

1. **Stash Your Current Changes**
   ```sh
   git stash save "WIP: adding new login feature"
   ```

2. **Switch to the Branch with the Bug**
   ```sh
   git checkout bugfix-branch
   ```

3. **Fix the Bug and Commit the Changes**
   ```sh
   # Make changes
   git add .
   git commit -m "Fix critical bug #99"
   ```

4. **Switch Back to Your Feature Branch**
   ```sh
   git checkout feature-branch
   ```

5. **Apply Your Stashed Changes**
   ```sh
   git stash apply
   ```

6. **Verify and Drop the Stash**
   ```sh
   git stash drop
   ```

Using `git stash` effectively allows you to manage your workspace efficiently, making it easier to handle interruptions and switch contexts without losing your progress.