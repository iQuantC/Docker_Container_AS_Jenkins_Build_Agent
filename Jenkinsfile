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
