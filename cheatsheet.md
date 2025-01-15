
### **Git Workflow Cheatsheet**
#### **Step 1: .gitignore Example**
The `.gitignore` file tells Git which files or directories to ignore. Here's a simple example:

```plaintext
# Ignore node_modules folder
node_modules/

# Ignore all .log files
*.log

# Ignore IDE configuration files
.vscode/
.idea/

# Ignore specific file
secrets.txt
```
Place the `.gitignore` file in the root of your repository.

---

#### **Step 2: Modify README.md**
1. Open the `README.md` file.
2. Find your name and update the line with information about yourself:
   ```markdown
   ### John Doe
   I am from Toronto, I love programming and hiking.
   ![My Avatar](avatar.png) <!-- Optional image -->
   ```
   *(If you add an image, ensure `avatar.png` is in the repository.)*

3. Stage, commit, and push changes:
   ```bash
   git add README.md
   git add avatar.png  # If adding a picture
   git commit -m "Added my bio to README.md"
   git push
   ```

---

#### **Step 3: Locating `git log`**
To find the commit ID:
1. Run the following command:
   ```bash
   git log
   ```
2. Look for the `commit` line, e.g.:
   ```plaintext
   commit aa0ccd6a610e6bca710420b11b1540694a703e6c
   Author: John Doe <john.doe@example.com>
   Date:   Wed Jan 15 12:01:33 2025 -0500
   ```
3. Copy the commit ID (e.g., `aa0ccd6a610e6bca710420b11b1540694a703e6c`).

---

#### **Step 4: Creating a Pull Request (PR)**
1. Navigate to your repository on GitHub.
2. Click **Compare & pull request**.
3. Write a meaningful description and submit the PR.

---

### **Resolving Merge Conflicts**
Conflicts occur when multiple changes overlap. To resolve:
1. **Identify the Conflict**: Git marks conflicts in files like this:
   ```plaintext
   <<<<<<< HEAD
   Line from your branch
   =======
   Line from main branch
   >>>>>>> main
   ```
2. **Fix the Conflict**:
   - Decide which lines to keep or combine.
   - Edit the file to remove conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).

3. **Stage and Commit the Resolved File**:
   ```bash
   git add <conflicted-file>
   git commit -m "Resolved merge conflict in <file>"
   ```

4. **Push Changes**:
   ```bash
   git push
   ```

---

#### **Helpful Git Commands**
- **View status**: `git status`
- **View changes**: `git diff`
- **Pull latest changes**: `git pull`
- **Check remote branches**: `git branch -r`
- **Force overwrite conflicts with theirs**: 
  ```bash
  git checkout --theirs <file>
  git add <file>
  git commit -m "Resolved conflict by accepting theirs"
  ```
