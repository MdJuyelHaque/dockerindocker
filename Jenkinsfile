pipeline {
    agent any
    stages {
        stage("Inside docker continer1") {
            steps {
                sh 'docker run -v /var/run/docker.sock:/var/run/docker.sock -ti docker'
                sh 'docker pull ubuntu'
                sh 'docker imges'
            }
        }
       stage("Build docker image inside docker") {
            steps {
                sh 'docker build -t test-image'
            }
        }
       stage("go inside ubunto continer") {
            steps {
                sh 'docker run -v /var/run/docker.sock:/var/run/docker.sock -ti test-image'
                sh 'docker run hello-world'
                sh 'docker imges'
                sh 'docker ps'
            }
        }
       
    }
}
