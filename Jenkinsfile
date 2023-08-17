pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub')
    }
    stages {
        stage("Clean-up") {
            steps {
                deleteDir()
            }
        }
        stage("Clone repo") {
            steps {
                sh "git clone https://github.com/AbhishekChandel1/jenkins/"
            }
        }
        stage("Log-in") {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage("Build") {
            steps {
                sh "docker build -f Dockerfile.app . -t abhishek7868/notejam2 "
            }
        }
        stage("Push-repo") {
            steps {
                sh "docker push abhishek7868/notejam2"
            }
        }
    }
}
