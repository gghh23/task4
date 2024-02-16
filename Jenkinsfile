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

                    sh "scp -i /var/lib/jenkins/ubuntu.pem /var/lib/jenkins/workspace/t44/dep.yml ubuntu@35.170.201.73:/home/ubuntu"
                    sh "ssh  -i /var/lib/jenkins/ubuntu.pem ubuntu@35.170.201.73 kubectl apply -f dep.yml"
                }
            }
        }
    }
}