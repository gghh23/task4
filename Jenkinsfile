pipeline {
    agent any
    stages {            
        stage("push"){
            steps {
                script {                   
                    sh "docker build . -t dmitiriy/nginx-rep-task4:latest"
                    sh "docker tag dmitiriy/nginx-rep-task4:latest dmitiriy/nginx-rep-task4:latest"
                    sh "docker push dmitiriy/nginx-rep-task4:latest"
                }
            }
        }
        stage("connect"){
            steps {
                script {
                    sh "pwd"
                    sh "scp -i /var/lib/jenkins/ubuntu.pem /var/lib/jenkins/workspace/t44/dep.yml ubuntu@54.144.68.232:/home/ubuntu"
                   
                }
            }
        }
    }
}