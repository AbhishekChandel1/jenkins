pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub')
    }
    stages {
        stage("Prepare") {
            steps {
                deleteDir()
                sh "git clone https://github.com/AbhishekChandel1/jenkins/"
            }
        }
        stage("Build") {
            steps {
                sh "docker build -t abhishek7868/notejam2 jenkins/"
            }
        }
        stage("Push-repo") {
            steps {
                sh "docker push abhishek7868/notejam2"
            }
        }
    }
}
