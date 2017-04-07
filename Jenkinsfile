pipeline {
  agent {
    docker {
      image 'python:3'
    }
    
  }
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
            
          },
          "Check versions": {
            sh 'python --version'
            
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