pipeline {
    agent any
    stages {            
        stage("push"){
            steps {
                script {                   
                    sh "docker build . -t dmitiriy/nginx-rep-task4:${BUILD_NUMBER}"
                    sh "docker tag dmitiriy/nginx-rep-task4:${BUILD_NUMBER} dmitiriy/nginx-rep-task4:${BUILD_NUMBER}"
                    sh "docker push dmitiriy/nginx-rep-task4:${BUILD_NUMBER}"
                }
            }
        }
        stage("connect"){
            steps {
                script {

                    sh "scp -i /var/lib/jenkins/ubuntu.pem /var/lib/jenkins/workspace/t44/dep.yml ubuntu@54.144.68.232:/home/ubuntu"
                    sh "ssh  -i /var/lib/jenkins/ubuntu.pem ubuntu@54.144.68.232 kubectl apply -f dep.yml"
                }
            }
        }
    }
}