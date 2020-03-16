pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw compile'
      }
    }

    stage('test') {
      steps {
        sh '''./mvnw test
'''
      }
    }

    stage('package') {
      steps {
        sh './mvnw package'
      }
    }

    stage('deploy') {
      steps {
        sh 'echo "Sucessfully Deployed"'
      }
    }
    
  }
  post {
    success {
      slackSend (color: '#00FF00', message: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
    }
  }
}
