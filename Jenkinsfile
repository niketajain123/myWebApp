pipeline {
  agent { label 'ssh_ubuntu' }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t web-app .'
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

