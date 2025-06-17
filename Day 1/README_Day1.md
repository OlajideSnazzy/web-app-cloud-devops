# 🚀 DevOps Project – Day 1: Setting Up a Web App in the Cloud

## 🔧 Project Overview  
Today, I started a DevOps project by creating a Java-based web app hosted on an EC2 instance. This forms the foundation for a CI/CD pipeline I'll be building over the course of 7 days.

---

## 🧠 Key Concepts Learned  
- Launching an **EC2 instance** on AWS  
- Working with **Key Pairs**  
- Establishing an **SSH connection** using terminal and VS Code  
- **Editing web files** (index.jsp) on a cloud server  
- Using **Maven** to scaffold a Java web application  

---

## 🔨 Tools & Technologies  
- **AWS EC2**  
- **VS Code** + Remote SSH  
- **Maven**  
- **Java**  
- **Terminal (PowerShell)**  

---

## Screenshots

###  PEM File Location
![PEM File](./Day 1/Screenshots/pem-file.png)  

###   Permission Setup in Terminal
![Permissions](./screenshots/terminal-permissions.png)

###   Project Folder in VS Code
![VS Code Project](./screenshots/vscode-explore.png)

###   Index.jsp Code
![Index.jsp Code](./screenshots/index.jsp.png)

###   SSH Connection Via Terminal
![SSH Connection Via Terminal](./screenshots/terminal-connection.png)

###   Java Installation On EC2 Instance
![Java Istallation](./screenshots/java-installation.png)

---

## 🗒️ Detailed Steps

### ✅ Launch EC2 Instance  
- Selected **Amazon Linux 2** as the AMI.  
- Created and downloaded a new **key pair** (`Project1.pem`).  

### ✅ Set File Permissions (Windows Equivalent of `chmod 400`)  
```powershell
icacls "Project1.pem" /inheritance:r
icacls "Project1.pem" /grant "Olajide:(R)"
icacls "Project1.pem" /remove "Users" "Administrators" "SYSTEM"
```

### ✅ SSH into EC2 Instance  
```bash
ssh -i "path\to\Project1.pem" ec2-user@<public-ip>
```

### ✅ Set Up Web App  
Used Maven to scaffold a Java web app:
```bash
mvn archetype:generate \
-DgroupId=com.nextwork.app \
-DartifactId=nextwork-web-project \
-DarchetypeArtifactId=maven-archetype-webapp \
-DinteractiveMode=false
```

### ✅ Explore and Edit index.jsp  
- Navigated project folders via VS Code Remote Explorer  
- Edited `index.jsp` inside `src/main/webapp` to add custom HTML

---

## 💡 Reflections  
> "One thing I didn’t expect was editing a `.jsp` file through the terminal-connected VS Code. It was fun. The most rewarding part was seeing the remote connection work."

- 🕒 Time Spent: ~3 hours  
- 🧠 Most Challenging: Setting up remote SSH access  
- ✅ Most Rewarding: Successfully editing project files in the cloud

---

## 📅 What’s Next (Day 2 Teaser)  
Tomorrow, I’ll continue configuring the environment, set up a Tomcat server, and prepare for CI/CD deployment. Stay tuned!
