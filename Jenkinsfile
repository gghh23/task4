pipeline {
    agent any
    stages {
        stage("build"){
            steps {
                script {
                    docker.build("dmitiriy/nginx-rep-task4:latest")
                }
            }
        }
            
        stage("push"){
            steps {
                script {
                    sh "docker login -u dmitriy -p ${dockerpwd}"
                    docker.image("dmitiriy/nginx-rep-task4:latest").push()
                }
            }
        }
            
    }
}