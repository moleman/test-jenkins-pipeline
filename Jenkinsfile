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
            
          },
          "Browser testing": {
            sh 'echo "Running browser tests"'
            
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