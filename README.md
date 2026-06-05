# Git_and_Github

# Git & GitHub Assignment

## 1. What is version control, and why is it essential in modern software development?

Version control is a system that records changes made to files over time so that specific versions can be recalled later. It allows developers to track modifications, collaborate effectively, and recover previous versions when mistakes occur.

### Importance:

* Maintains a history of changes.
* Enables collaboration among multiple developers.
* Prevents accidental loss of code.
* Supports experimentation without affecting the main project.
* Facilitates debugging by identifying when bugs were introduced.

---

## 2. Difference Between Centralised and Distributed Version Control Systems

### Centralised Version Control System (CVCS)

Examples: SVN, CVS

Characteristics:

* A single central server stores the complete repository.
* Developers check out files from the central server.
* Requires network access for many operations.

### Distributed Version Control System (DVCS)

Example: Git

Characteristics:

* Every developer has a complete copy of the repository.
* Most operations can be performed offline.
* Multiple backup copies naturally exist.

### Advantages of Git's Distributed Model

* Faster operations because actions occur locally.
* Better fault tolerance.
* Offline work capability.
* Easier branching and merging.
* Enhanced collaboration flexibility.

---

## 3. Git vs GitHub

### Git

Git is a distributed version control tool used to track changes in source code.

### GitHub

GitHub is a cloud-based platform that hosts Git repositories and provides collaboration features.

### Problem GitHub Solves

Git alone manages version history but does not provide:

* Cloud hosting
* Pull requests
* Code reviews
* Team collaboration tools
* Issue tracking
* Project management features

### Relationship

Git is the engine that tracks changes, while GitHub provides a platform where Git repositories can be shared and managed collaboratively.

---

## 4. Why Version Control Matters Even for Solo Developers

Version control remains valuable even when only one developer works on a project.

Reasons:

* Provides a complete history of changes.
* Makes it easy to revert mistakes.
* Allows experimentation using branches.
* Serves as an automatic backup system.
* Helps track progress over time.
* Makes future collaboration easier if additional developers join.

Without version control, a developer may lose important work, struggle to identify bugs, or waste time manually managing multiple file copies.

---

## 5. Everyday Analogy for Git Commits, Branches, and Merges

Imagine writing a book.

### Commit

Each time you finish a chapter and save it, you take a photograph of the entire manuscript. That photograph represents a commit.

### Branch

Suppose you want to try an alternative ending without changing the original story. You create a separate copy and work there. That copy is a branch.

### Merge

After deciding the alternative ending is better, you bring those changes back into the main book. This process is called merging.

Git works similarly:

* Commits are saved checkpoints.
* Branches are separate workspaces.
* Merges combine completed work.

---

## 6. What is a Snapshot in Git?

A snapshot is Git's record of the entire project at a specific point in time.

### Git Snapshot Model

Git stores snapshots of files.

### Delta-Based Systems

Traditional systems store differences between file versions.

### Difference

| Git Snapshot Model   | Delta Model             |
| -------------------- | ----------------------- |
| Stores project state | Stores file differences |
| Faster retrieval     | Requires reconstruction |
| Better performance   | Can be slower           |

---

## 7. Three Git Hosting Platforms Besides GitHub

### GitLab

Features:

* Built-in CI/CD
* Self-hosting options
* Comprehensive DevOps tools

### Bitbucket

Features:

* Integration with Atlassian products
* Jira support
* Good for enterprise teams

### Azure Repos

Features:

* Microsoft ecosystem integration
* Enterprise security
* Supports Git and TFVC

### Factors Affecting Choice

* Cost
* CI/CD requirements
* Security policies
* Existing tool ecosystem
* Team size

---

## 8. Git Installation Verification

### Command

```bash
git --version
```

### Output

```bash
git version X.X.X
```

### Screenshot

*Insert screenshot here.*

---

## 9. Configure Global Git Identity

### Commands

```bash
git config --global user.name "Your Name"

git config --global user.email "your@email.com"
```

### Verify

```bash
git config --global --list
```

### Sample Output

```bash
user.name=Your Name
user.email=your@email.com
```

### Screenshot

*Insert screenshot here.*

---

## 10. Global vs Local Configuration

### Global Configuration

Applies to all repositories on the computer.

```bash
git config --global user.name "Kasiemobbi Eke"
```

### Local Configuration

Applies only to one repository.

```bash
git config --local user.name "Work Account"
```

### Example Use Case

A developer uses:

* Personal GitHub account for personal projects.
* Company account for work projects.

Local configuration prevents mixing identities.

---

## 11. Why Git Email Should Match GitHub Email

Matching emails allows GitHub to correctly associate commits with your account.

If emails differ:

* Contributions may not appear on your profile.
* Commit history may show unknown authors.
* Contribution graphs become inaccurate.

---

## 12. Git's Three-Area Architecture

### Working Directory

Where files are actively edited.

### Staging Area (Index)

Where selected changes are prepared for commit.

### Repository

Permanent storage of committed snapshots.

### Workflow

```text
Working Directory
       ↓
git add
       ↓
Staging Area
       ↓
git commit
       ↓
Repository
```

---

## 13. What is HEAD?

HEAD is a pointer to the current commit being worked on.

### Detached HEAD

Occurs when checking out a specific commit rather than a branch.

Example:

```bash
git checkout abc123
```

### Safe Recovery

Create a branch:

```bash
git switch -c new-branch
```

or return:

```bash
git switch main
```

---

## 14. Initialise Repository and Create Commits

### Commands

```bash
mkdir git-demo

cd git-demo

git init

touch file1.txt
touch file2.txt
touch file3.txt

git add file1.txt
git add file2.txt

git commit -m "feat: add first two files"

git add file3.txt

git commit -m "feat: add third file"
```

### Log Output

```bash
git log --oneline
```

Example:

```text
d5f6g7 feat: add third file
a1b2c3 feat: add first two files
```

---

## 15. git diff, git diff --staged, and git diff HEAD

### Scenario

```bash
echo "change1" >> file1.txt

git add file1.txt

echo "change2" >> file2.txt
```

### Unstaged Changes

```bash
git diff
```

Shows changes in file2.txt.

### Staged Changes

```bash
git diff --staged
```

Shows staged changes in file1.txt.

### All Changes

```bash
git diff HEAD
```

Shows both staged and unstaged modifications.

---

## 16. Characteristics of a Great Commit Message

1. Clear and concise.
2. Uses imperative mood.
3. Describes what changed.
4. Explains why when necessary.
5. Follows conventions.

### Examples

```text
feat: add user authentication

fix: resolve login validation bug

docs: update installation instructions
```

---

## 17. Useful git log Commands

### One Line

```bash
git log --oneline
```

### Graph

```bash
git log --graph --oneline
```

### Since

```bash
git log --since="7 days ago"
```

### Author

```bash
git log --author="John"
```

Explain each output using your repository screenshots.

---

## 18. reset vs revert vs restore

### git reset

Moves branch pointers.

```bash
git reset --hard HEAD~1
```

Risk:
Can permanently discard work.

### git revert

Creates a new commit that undoes changes.

```bash
git revert HEAD
```

Safest for shared repositories.

### git restore

Restores file contents.

```bash
git restore file.txt
```

Safely discards uncommitted changes.

---

## 19-33 Practical GitHub Exercises

The remaining questions require live GitHub activities and screenshots.

For each exercise include:

### Evidence

* Commands executed.
* Terminal screenshots.
* GitHub screenshots.
* Pull request URLs.
* Repository URLs.

Topics include:

1. Creating repositories.
2. HTTPS and SSH cloning.
3. Fetch vs Pull.
4. Upstream remotes.
5. Remote tracking branches.
6. Pushing commits.
7. Writing README.md.
8. Branching and merging.
9. Merge conflicts.
10. Rebase workflows.
11. Git Flow.
12. GitHub Flow.
13. Trunk-Based Development.
14. Feature delivery cycle.
15. Forking repositories.
16. Creating pull requests.
17. Performing code reviews.

Since these require interaction with actual GitHub repositories, screenshots and URLs must be generated from your own work and cannot be fabricated.

---

# Conclusion

Git is a powerful distributed version control system that enables developers to track changes, collaborate effectively, and manage software projects safely. GitHub extends Git by providing cloud hosting and collaboration features, making it an essential platform for modern software development workflows.
