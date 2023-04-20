pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
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
         stage('status') {
            steps {
                echo 'here is the status..'
                echo "the buils number is ${BUILD_NUMBER}"
                echo "the job name is ${JOB_NAME}"
                echo "git details ${GIT_BRANCH}"
                echo "${GIT_AUTHOR_NAME}"
            }
        }
    }
}
