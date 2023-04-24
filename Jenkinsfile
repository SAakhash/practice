pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t homepage .'
                echo 'Building..'
                echo 'hello world from build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Push Docker image to Docker Hub') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerHub', usernameVariable: 'DOCKER_HUB_USERNAME', passwordVariable: 'DOCKER_HUB_PASSWORD')]) {
          sh 'docker login -u $DOCKER_HUB_USERNAME -p $DOCKER_HUB_PASSWORD'
          sh 'docker push <DOCKER_HUB_USERNAME>/homepage'
        }
      }
    }
         stage('status') {
            steps {
                echo 'here is the status..'
                echo "the buils number is ${BUILD_NUMBER}"
                echo "the job name is ${JOB_NAME}"
                echo "git details ${GIT_BRANCH}"
                
            }
        }
    }
}
