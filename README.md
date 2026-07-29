# 🚀 Jenkins Remote Build Agent using Docker

## 📌 Project Overview

This project demonstrates how to configure a remote Jenkins build agent using Docker and SSH. The Jenkins Controller runs on Kali Linux, while an Ubuntu 24.04 Docker container acts as the remote build agent. Jenkins pipelines are executed on the remote Docker agent instead of the Jenkins controller.

---

## 🎯 Objective

- Configure Jenkins Controller on Kali Linux.
- Create a remote Ubuntu Docker container.
- Configure SSH communication between Jenkins Controller and Docker Agent.
- Connect the Docker container as a Jenkins Agent.
- Execute Jenkins jobs remotely.

---

## 🛠️ Technologies Used

- Jenkins
- Docker
- Ubuntu 24.04
- Kali Linux
- OpenSSH Server
- OpenJDK 21
- Jenkins Pipeline (Groovy)

---

## 🏗️ Architecture

                +-----------------------+
                |   Jenkins Controller  |
                |     Kali Linux VM     |
                +-----------+-----------+
                            |
                        SSH Connection
                            |
                +-----------v-----------+
                |   Docker Container    |
                |     Ubuntu 24.04      |
                |   Jenkins Remote Agent|
                +-----------+-----------+
                            |
                     Executes Pipeline

---

## ⚙️ Project Workflow

1. Installed Jenkins on Kali Linux.
2. Pulled the Ubuntu 24.04 Docker image.
3. Created an Ubuntu Docker container.
4. Installed OpenJDK 21 inside the container.
5. Installed and configured OpenSSH Server.
6. Created a Jenkins user inside the container.
7. Connected the Docker container to Jenkins using SSH.
8. Configured the Docker container as a Jenkins Agent.
9. Created and executed a Jenkins Pipeline successfully on the remote Docker agent.

---

## 📂 Repository Structure

```text
Jenkins-Remote-Build-Agent/
│
├── README.md
├── Jenkinsfile
└── Screenshots/
```

---

## 📜 Jenkins Pipeline

```groovy
pipeline {
    agent {
        label 'docker'
    }

    stages {
        stage('System Info') {
            steps {
                sh 'hostname'
                sh 'whoami'
                sh 'pwd'
            }
        }
    }
}
```

---

## 📸 Project Screenshots

### Jenkins Dashboard

### Jenkins Nodes

### Docker Agent Connected

### Docker Agent Pipeline Output

### Ubuntu Agent Pipeline Output



---

## ✅ Pipeline Output

```text
Running on docker-agent

hostname
docker-agent

whoami
jenkins

pwd
/home/jenkins/workspace/docker-agent-test

Finished: SUCCESS
```

---

## 🎓 Learning Outcomes

- Jenkins Controller and Agent Architecture
- Docker as a Remote Jenkins Agent
- SSH-based Agent Configuration
- Jenkins Distributed Builds
- Jenkins Pipeline Execution
- Remote Build Automation

---

## 💻 Author

**Shreya Lokhande**

GitHub: https://github.com/shreyal11
