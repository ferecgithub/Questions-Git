# Answers - Git

1. What is Git?
    Git is a distributed version control system used in software development processes, providing developers with the ability to track project file history, manage changes, collaborate, and track code.

2. What is the difference between "git pull" and "git fetch" commands?
    The difference between "git pull" and "git fetch" commands is that "git pull" not only retrieves changes from the remote repository but also integrates them into the local branch, whereas "git fetch" only downloads changes from the remote repository to the local repository without merging them into the current branch.

3. If our teammate says "I've pushed my code, continue from where I left off with my development," and we can't fetch their pushed code to our local repository using "git pull," where might mistakes have been made?
    * **Conflicting changes**: This is one of the most common issues in this context. If a person has made changes in their local working environment, the "git pull" command cannot be executed.
    * **Permission issue**: The person may face permission restrictions when connecting to the remote server.
    * **Pushing to the wrong branch:** The developer may have mistakenly sent the code to the wrong branch. In this case, it would be helpful to clearly specify the branch that has been pushed to.

4. What does "origin" refer to in the "git fetch origin" command?
    "origin" is an alias for a remote Git repository. While traditionally it's given as the first repository name, we can assign different names as well. This is particularly useful in projects with multiple remote repositories.

5. What does the term "HEAD" represent?
    "HEAD" represents the current position where operations are being performed in a git repository. More specifically, "HEAD" typically points to the latest commit in the current working branch. It indicates the branch being worked on and its latest state.

6. What exactly is the region referred to as "Staging Area" or "Index"?
    The Staging Area represents an intermediate area in a Git repository where changes are prepared and held to be included in a subsequent commit. This area allows for organizing and reviewing changes before they are added to commits.

7. What does "Untracked file" mean?
    An untracked file refers to a file that has not yet been added to the staging area. Git will not track or save changes for this file, and will not store any information about it.

8. What happens if we delete the ".git" folder?
    If we delete this folder, all the changes, history, and tracking information related to the Git repository we have locally stored for the project will be erased.

9. If we want a "ReadMe.md" file to be automatically created every time we use the "git init" command in our local environment, what should we do?
    We can use the Git template for this purpose. We can follow these steps:
    1. We create a "ReadMe.md" file in our local working environment. This will serve as a template for us when creating a new repository.
    2. Let's save the address of the Git template with git config as follows (we will provide the address where we created ReadMe.md instead of /path/to/your/template/directory):
    ```
        git config --global init.templateDir /path/to/your/template/directory
    ```
    3. We can create a repository with the "git init" command. In this case, "ReadMe.md" will be automatically created for us.

10. What is the "branch" structure mentioned in Git? What does it provide us?
    In the Git system, the branch structure allows developers to work on different features or changes in parallel on the same project. By creating bug fixes or new feature branches, developers avoid polluting the main production branch. This also provides isolation.

11. How can we create a new "branch" from scratch?
    In Git system, there are two primary ways to create a branch from scratch, both of which accomplish the same task but differ only in terms of version.
    1. We can create a branch using the "switch" keyword, which is the recommended method after version 2.23:
    ```
        git switch -c <branch_name>
    ```
    2. We can create a branch using the "checkout" keyword, which is an older method:
    ```
        git checkout -b <branch_name>

12. How can we switch to an existing "branch"?
    You can switch to an existing branch using the "switch" and "checkout" keywords.
    1. Switching to a branch using the "switch" keyword, which is the recommended method after version 2.23:
    ```
        git switch <branch_name>
    ```
    2. Switching to a branch using the "checkout" keyword, which is an older method:
    ```
        git checkout <branch_name>

13. If we want to fetch only a specific branch while using the "git clone" command, how can we do it?
    If we want to clone a specific branch, we should use the -b or --branch flag. The command template is as follows:
    ,,,
        git clone -b <branch_name> <repository_address>
    ,,,

14. What does "Merge conflict" mean?
    A "merge conflict" refers to conflicts encountered during the merging process that Git cannot automatically resolve. These conflicts may arise from changes made to the same line of a file in different branches or situations where a file is deleted in one branch while being modified in another. In cases where Git cannot resolve the conflict, manual intervention by the user is required. The user must review the conflicting files, resolve the conflicting changes, and then commit their resolutions.

15. What information can we see with the "git log" command?
    The "git log" command is used to display the commit history in a Git repository. With this command, unique identifiers in the form of hash codes, the author's name and email, date and time information, commit message, and a list of changes made are shown. You can request either a summary (using the --oneline flag) or a detailed view (using the -p flag).

16. How many different sets of changes can we see between two states using "git diff"?
    The "git diff" command is primarily used to compare four different scenarios:
    1. To see the changes between two commits:
    ```
        git diff <commit1> <commit2>
    ```
    2. To see the changes between two different branches:
    ```
        git diff <branch1> <branch2>
    ```
    3. To see the changes between two tags:
    ```
        git diff <tag1> <tag2>
    ```
    4. To see the changes between your working directory and the last commit:
    ```
        git diff HEAD
    ```

17. What do we revert with Git reset?
    The "git reset" command is used to reset the pointer (HEAD) and the working directory to a specific previous state. This is useful for undoing or modifying changes made. There are 3 types of flags that can be used:

    1. Soft reset (`--soft`): It moves the pointer and the directory to a specific previous commit (or any specified position), but keeps your changes in the working directory (staged). It allows you to revert to a previous state as if you haven't committed yet.
    2. Mixed reset (`--mixed`): It behaves like a soft reset, but removes changes from the working directory (staged) and reverts tracked files to their state before changes. It cancels changes in the working directory as if you haven't committed yet but prepares your files for modification.
    3. Hard reset (`--hard`): It moves the pointer to a specific previous position and deletes all changes and untracked files. It is used when you want to fully revert to a specific previous state and removes all changes made.

18. What is the difference between "git commit" and "git push"?
    * The "git commit" command saves changes in the local repository to a tracked history. This allows changes to be tracked and rolled back if necessary.
    * The "git push" command sends changes from the local repository to a remote repository (such as GitHub or Bitbucket). This allows changes to be shared with other collaborators and creates a centralized version history for the project.

19. What is an Atomic commit?
    Atomic commit is committing a feature or a change in the smallest, meaningful, and consistent way possible. This ensures that commits are made in a consistent and clean manner, making it easier to revert if necessary.

20. What does Repository mean?
    Repository, a place where the files and project history of a software project are stored. Typically, a Git repository can be thought of as a directory containing project files and a database that includes the history, changes, and version history of these files. The repository hosts project files and enables developers to work on, make changes to, revert, and share these files. Therefore, the repository serves as the central repository of a software project and maintains the project history.

21. What is "git tag"? How does it differ from "git branch"?
    "git tag" is a Git command used to add tags to a specific commit or state (such as a release or published software version). These tags specify the status or version of the project at a specific point by assigning a meaningful name or number. They are typically used to mark software releases or indicate significant milestones.
    On the other hand, the "git branch" command is used to list existing branches in a Git repository, create new branches, delete an existing branch, or switch a branch. While creating a new branch for adding a new feature or fixing a bug, "git tag" is used to mark specific points in a project. In other words, while "git branch" facilitates branch creation and management, "git tag" is used to assign meaningful names to specific points.

22. What third-party tools and applications can we use to visually interact with Git?
    For this purpose, we can use third-party tools such as SourceTree, GitHub Desktop, GitKraken.

23. What is the difference between "GitHub" and "git"? What are other similar sites like GitHub? Could you list usernames on GitHub or other sites?
    GitHub is a remote repository that uses the Git system. We can think of it as a database. Git, on the other hand, is a version control system. It provides developers with the ability to track the history of project files, manage changes, collaborate, and track code. Apart from GitHub, there are also remote repositories such as GitLab, BitBucket, GitKraken, SourceForge, and Launchpad. Personally, I use GitHub and my GitHub address is [ferecgithub](https://github.com/ferecgithub).

24. What is the difference between the main or master branch and other branches?
    The main or master branch is the default branch created initially. This branch is usually restricted to developers other than high-level developers for stability and security reasons. Typically, tested and functioning versions are merged into the main branch.

25. What is the ".gitignore" file and what is it used for? - (Thanks @madenyasin)
    This tool allows us to specify files that we do not want to send to the Git repository, want to keep private, or are specific to the computer we are working on. This way, we can prevent the repository from growing with unnecessary files and mitigate some security vulnerabilities.

26. What is "git push origin --delete branch_name" and what is it used for?