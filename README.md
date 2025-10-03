# Docker_Container_AS_Jenkins_Build_Agent
In this video, we walk you through a detailed tutorial on setting up a Jenkins Master using Docker and integrating it with a Docker container that serves as a Jenkins Build Agent. If you're looking to streamline your CI/CD pipelines with Jenkins and Docker, this guide is perfect for you!

### Jenkinsfile
```sh
pipeline {
  agent { label 'docker-agent' }
  stages {
    stage('Clone Repository') {
      steps {
        git branch: 'main', credentialsId: 'my-vm-token', url: 'https://github.com/iQuantC/Complete_CICD_02.git'
      }
    }
    stage('Check curl & ping version') {
      steps {
        sh '''
          curl -V
          ping -V
        '''
      }
    }
  }
}
```
