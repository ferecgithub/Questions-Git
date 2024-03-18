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

18. What is the difference between "git commit" and "git push"?
19. What is an Atomic commit?
20. What does Repository mean?
21. What is "git tag"? How does it differ from "git branch"?
22. What third-party tools and applications can we use to visually interact with Git?
23. What is the difference between "GitHub" and "git"? What are other similar sites like GitHub? Could you list usernames on GitHub or other sites?
24. What is the difference between the main or master branch and other branches?
25. What is the ".gitignore" file and what is it used for?
26. What is "git push origin --delete branch_name" and what is it used for?