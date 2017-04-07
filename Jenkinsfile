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
        parallel(
          "Deploy": {
            sh 'echo "Deploy"'
            
          },
          "Stage": {
            echo 'Test'
            
          }
        )
      }
    }
    stage('Clean up') {
      steps {
        deleteDir()
      }
    }
  }
}