pipeline {
  agent any
  tools {
    maven 'Maven 3.5.2'
    }
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean package'
        }
      post {
        success {
          echo 'Now archiving...'
          archiveArtifacts artifacts: '**/target/*.war'
        }
      }
    }
  }
}
