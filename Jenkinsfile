pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo "building"
      }
    }
    stage('Test') {
      steps {
        sh 'echo "Running tests..."'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "Deploying app..."'
      }
    }
  }
  post {
    success {
      echo 'Build succeeded!'
    }
    failure {
      echo 'Build failed!'
    }
  }

