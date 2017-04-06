pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        parallel(
          "Test": {
            echo 'Running tests'
            
          },
          "Lint": {
            sh 'echo "Running Lint"'
            
          }
        )
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "Deploy"'
      }
    }
    stage('Clean up') {
      steps {
        deleteDir()
      }
    }
  }
}