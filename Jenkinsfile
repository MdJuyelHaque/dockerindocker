pipeline {
    agent any
    stages {
        stage("Inside docker continer1") {
            steps {
                sh 'docker run -v /var/run/docker.sock:/var/run/docker.sock docker'
                sh 'docker pull ubuntu'
                sh 'docker images'
            }
        }
       stage("Build docker image inside docker") {
            steps {
                sh 'docker build -t test-image .'
            }
        }
       stage("go inside ubunto continer") {
            steps {
                sh 'docker run -v /var/run/docker.sock:/var/run/docker.sock test-image'
                sh 'docker run hello-world'
                sh 'docker images'
                sh 'docker ps'
            }
        }
       
    }
}
