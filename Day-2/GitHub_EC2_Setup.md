
# Setting Up Git and GitHub on an EC2 Instance

## 1. Installing Git

In this step, I’ll be installing Git on the EC2 instance (Linux server).  
**Git** is a version control tool used by developers to track and manage changes made to code identifying who made what changes and when. It’s essential for tasks like version control, which helps teams collaborate more efficiently on projects.

I installed Git using the following commands:

```bash
sudo dnf update -y  
sudo dnf install git -y
```

---

## 2. Setting Up GitHub and Creating a Repository

Next, I set up a **GitHub account** and created a **GitHub repository**.  
GitHub is a cloud-based platform that allows developers to store and share code online. It works with Git to manage a project’s version history.

A **Git repository (repo)** on GitHub is essentially a folder that contains all the files related to a project, along with a record of all changes made to those files. Since GitHub is cloud based, repositories can be accessed from anywhere.

---

## 3. Initializing a Local Git Repository

In this stage, I set up a **local Git repository** inside my web app project folder on the EC2 instance. This allows me to connect the local project with the remote GitHub repository.

To initialize the local repo, I ran:

```bash
git init
```

This command sets up Git tracking in the current directory. After running it, I received this confirmation:

```
Initialized empty Git repository in /home/ec2-user/nextwork-web-project/.git/
```

In Git, a **branch** is a copy of the repository used to make changes independently before merging them back into the main codebase — usually the `main` or `master` branch.

---

## 4. Staging and Committing Code

The first Git command I ran was:

```bash
git add .
```

This stages all modified files for commit.

Next:

```bash
git commit -m "Initial commit"
```

This takes a snapshot of the staged changes.

Finally:

```bash
git push -u origin master
```

This pushes the committed changes to the GitHub repository. The `-u origin master` flag sets `origin` as the default remote and `master` as the default branch, so future pushes can be done with just `git push`.

---

## 5. SSH Authentication and Git Configuration

To push changes over SSH, I used an authentication key stored on the EC2 instance. This enabled secure communication between the instance and GitHub.

Git also requires a **username and email** for commits. If not manually configured, it uses system defaults, which may not correctly identify the user.

I confirmed my Git identity and recent commits by running:

```bash
git log
```

This displayed my configured username, email, and the timestamp of the last commit.

---

## 6. Making Changes and Pushing to GitHub

To test Git in action, I made changes to the `index.jsp` file in my project. Initially, the changes didn’t appear in GitHub because I forgot to commit them.

After running the following commands:

```bash
git add .
git commit -m "Updated changes"
git push
```

— the changes were staged, committed, and successfully pushed to GitHub.
