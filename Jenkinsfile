pipeline {
    agent any
    stages {            
        stage("push"){
            steps {
                script {
                    
                    sh "docker build . -t dmitiriy/nginx-rep-task4:latest"
                    sh "docker tag dmitiriy/nginx-rep-task4:latest dmitiriy/nginx-rep-task4:latest"
                    sh "su ubuntu"
                    sh "docker push dmitiriy/nginx-rep-task4:latest"
                }
            }
        }
            
    }
}