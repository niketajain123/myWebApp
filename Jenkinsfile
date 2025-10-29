pipeline {
  agent any
  environment {
    DOCKERHUB_CREDENTIALS = 'dockerhub'
    IMAGE_NAME = 'niketa15jain/wademo'
    IMAGE_TAG = "${BUILD_NUMBER}"
  }
  stages {
    stage('Build and Push') {
      steps {
        script {
          echo "Building Docker image with tag: ${IMAGE_TAG}"
          docker.build("${IMAGE_NAME}:${IMAGE_TAG}")
          echo "Pushing Docker image to DockerHub..."
          docker.withRegistry('https://index.docker.io/v1/',"${DOCKERHUB_CREDENTIALS}") {
            docker.image("${IMAGE_NAME}:${IMAGE_TAG}").push()
          }
        }
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
}
