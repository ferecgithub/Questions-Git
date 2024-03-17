# Cevaplar - Git

- What is Git?
    Git is a distributed version control system used in software development processes, providing developers with the ability to track project file history, manage changes, collaborate, and track code.

- What is the difference between "git pull" and "git fetch" commands?
    The difference between "git pull" and "git fetch" commands is that "git pull" not only retrieves changes from the remote repository but also integrates them into the local branch, whereas "git fetch" only downloads changes from the remote repository to the local repository without merging them into the current branch.

- If our teammate says "I've pushed my code, continue from where I left off with my development," and we can't fetch their pushed code to our local repository using "git pull," where might mistakes have been made?
    * **Conflicting changes**: This is one of the most common issues in this context. If a person has made changes in their local working environment, the "git pull" command cannot be executed.
    * **Permission issue**: The person may face permission restrictions when connecting to the remote server.
    * **Pushing to the wrong branch:** The developer may have mistakenly sent the code to the wrong branch. In this case, it would be helpful to clearly specify the branch that has been pushed to.

- What does "origin" refer to in the "git fetch origin" command?
    "origin" is an alias for a remote Git repository. While traditionally it's given as the first repository name, we can assign different names as well. This is particularly useful in projects with multiple remote repositories.

- What does the term "HEAD" represent?
    "HEAD" represents the current position where operations are being performed in a git repository. More specifically, "HEAD" typically points to the latest commit in the current working branch. It indicates the branch being worked on and its latest state.

- What exactly is the region referred to as "Staging Area" or "Index"?
    The Staging Area represents an intermediate area in a Git repository where changes are prepared and held to be included in a subsequent commit. This area allows for organizing and reviewing changes before they are added to commits.

- What does "Untracked file" mean?
    An untracked file refers to a file that has not yet been added to the staging area. Git will not track or save changes for this file, and will not store any information about it.

- What happens if we delete the ".git" folder?
    If we delete this folder, all the changes, history, and tracking information related to the Git repository we have locally stored for the project will be erased.

- If we want a "ReadMe.md" file to be automatically created every time we use the "git init" command in our local environment, what should we do?
- What is the "branch" structure mentioned in Git? What does it provide us?
- How can we create a new "branch" from scratch?
- How can we switch to an existing "branch"?
- If we want to fetch only a specific branch while using the "git clone" command, how can we do it?
- What does "Merge conflict" mean?
- What information can we see with the "git log" command?
- How many different sets of changes can we see between two states using "git diff"?
- What do we revert with Git reset?
- What is the difference between "git commit" and "git push"?
- What is an Atomic commit?
- What does Repository mean?
- What is "git tag"? How does it differ from "git branch"?
- What third-party tools and applications can we use to visually interact with Git?
- What is the difference between "GitHub" and "git"? What are other similar sites like GitHub? Could you list usernames on GitHub or other sites?
- What is the difference between the main or master branch and other branches?
- What is the ".gitignore" file and what is it used for?
- What is "git push origin --delete branch_name" and what is it used for?