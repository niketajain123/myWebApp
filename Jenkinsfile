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
        echo "Running tests..."
      }
    }
    stage('Deploy') {
      steps {
        echo "Deploying app..."
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
