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
                    sh "scp -i /home/ubuntu/ubuntu.pem dep.yml ubuntu@54.144.68.232:/home/ubuntu"
                    sh "ssh -i /home/ubuntu/ubuntu.pem ubuntu@54.144.68.232 kubectl apply -f dep.yml" 
                }
            }
        }
    }
}