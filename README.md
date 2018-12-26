# gitlab-jenkins-sonarqube
A working docker-compose of a CI system with GitLab, Jenkins, and SonarQube.

## Instructions

### Starting the instance

Clone this repository (or just download the files). Go to the repository directory and run:

```bash
docker-compose up -d
```

These are the URLs for various services:
* GitLab - http://localhost:8000
* Jenkins - http://localhost:8080
* SonarQube - http://localhost:9000

Of course, if these ports are taken up by something else on your machine, the command will fail. In that case, either free up that port or change the port in docker-compose.yml file.

As Jenkins installation requires a secret key which is sent to the logs, use `docker logs` to get the key. Run this command:

```bash
docker logs gitlab_jenkins_1 | less
```

### Shutting down

Run this command:

```bash
docker-compose down
```

The data is persisted through various volumes. This means you can rerun `docker-compose up -d` to get back the system as it was before you shut it down. If you want to remove all the volumes as well, run:

```bash
docker-compose down -v
```
