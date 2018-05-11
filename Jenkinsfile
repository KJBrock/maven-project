pipeline {
  agent any
  tools {
    maven 'localMaven'
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

    stage('DeployToStaging') {
      steps {
        build job: 'deploy-to-staging'
        }
    }
  }
}
