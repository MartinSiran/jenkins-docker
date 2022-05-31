# jenkins-docker

Jenkins running on docker using docker compose.
Bonus container to use agent docker in Jenkins.

## prerequisites

- docker installed on your device

## usage

- `docker compose up [-d]` to run
- `docker compose down` to stop

### using docker agent
- example Jenkinsfile (replace `image` as necessary)
```
pipeline {
    agent { docker { image 'maven:3.8.4-openjdk-11-slim' } }
    stages {
        stage('build') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
```
