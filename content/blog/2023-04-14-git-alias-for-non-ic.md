+++
title = "don't teach git, alias it"
date = 2023-04-11
draft = true
authors = ["arnau"]

[taxonomies]
categories = ["programming"]
tags = ["programming"]

[extra]
lang = "en"
toc = true
show_comment = true
math = false
mermaid = false
+++
---

# Don't teach git, alias it

Non-technical team members like product owners and managers play a crucial role in software projects. However, they may not have the technical expertise to use Git effectively. Git aliases can simplify the process, enabling non-technical team members to easily make changes to the code and collaborate with technical team members.

For instance, suppose a product manager needs to modify the documentation of a public portal. Traditionally, she would need to clone the project, edit the content, and then use Git commands to push the changes. But this process can be complex and overwhelming for someone without a technical background. Instead, we can provide Git aliases to simplify the process. By using aliases, the product manager can push her changes with a single command without having to learn Git's abstractions.

Here are the commands required for the example:

1. git clone <repository URL> - to clone the project from the repository to the local machine.
2. Use an editor to make the necessary changes to the documentation.
3. git add . - to add all the changes made to the documentation to the staging area.
4. git commit -m "Commit message" - to commit the changes to the local repository with a descriptive commit message.
5. git push - to push the changes to the remote repository on GitHub.
6. Open a pull request on GitHub to merge the changes into the main branch of the project.

Since all changes are made within a single project, we can simplify the process even further by creating a single Git alias to handle all of the necessary commands.

1. git clone <repository URL> - to clone the project from the repository to the local machine. This step would only need to be done once.
2. Use an editor to make the necessary changes to the documentation.
3. git myalias - To do steps 3, 4, 5, 6 all together.

## operational

Before non-technical team members can contribute to a software project using Git, there are several preliminary tasks that need to be completed. These tasks are essential for creating a collaborative and streamlined development process. Here are the operational steps required:

- Install Git: The non-technical team member needs to install Git on their computer to interact with the project repository.
- Install Tooling: Depending on the project, there may be additional tools that need to be installed, such as Node.js or Python.
- Install a text editor: A text editor like Visual Studio Code or Sublime is required to make changes to the codebase.
- Configure a GitHub account: The non-technical team member needs a GitHub account to contribute to the project. The technical team members can assist with this step.
- Configure SSH keys: To securely interact with the GitHub repository, the non-technical team member needs to configure SSH keys. This is done by generating a public/private key pair and adding the public key to the GitHub account.
- Tutorial: Finally, the non-technical team member should be given a tutorial on how to use Git aliases to contribute to the project. This tutorial should cover the entire process, from making changes to pushing them to the repository.

By completing these operational steps, non-technical team members can easily contribute to a software project using Git aliases. This creates a more efficient and collaborative development process, empowering everyone on the team to contribute to the project's success.

## uses cases

It's important to help non-software engineers contribute to a project not only with their first commit, but also to maintain the project and fix mistakes. Here are some common situations:

### Push a pull request

When you have your project up-to-date in a folder, you may want to make changes and open a pull request. One way to do this is by using a Git alia

### Keep the project up-to-date

As the project evolves, non-technical team members may need to keep it up-to-date by making updates and changes to reflect product updates. However, if changes have been made but not saved, caution is advised.

To keep the project up-to-date, non-technical team members can either update the project or push a change, but they should be aware that doing so will result in the loss of any unsaved work.

For simpler changes, a non-software engineer may find it easier to simply copy and paste the file they want to keep into another folder instead of dealing with the complexities of git merges or rebases.

### Fixing mistakes

For simple contributions, such as adding text to a file, a non-technical contributor's mistake can be easily fixed using a good text editor.

It's best to avoid tackling complex or difficult problems. Our focus is on simple documentation tasks. It doesn't make sense to try to modify multiple files or return to an intermediate state.