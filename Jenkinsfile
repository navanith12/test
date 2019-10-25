pipeline {
    agent any 
    stages {
        stage('Build'){
            steps{
                bat 'mvn clean package'
                bat "docker build . -t dockertest:${env.BUILD_ID}"
                bat "docker login"
                bat "docker tag dockertest:${env.BUILD_ID} samhitha1193/dockertest:${env.BUILD_ID}"
                bat "docker push samhitha1193/dockertest:${env.BUILD_ID}"
            }
        }
    }
}
