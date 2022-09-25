pipeline {
    agent any
    tools {
        maven 'mymaven'
    }
    environment {
        imageName = 'ragh19/springboot-myproj:'
    }
    stages {
        stage('Pulling the code from Github') {
            steps {
                git '=https://github.com/Davanand1/Spring-boot.git'
            }
        }
        stage('Bulding the Java App') {
            steps {
                sh 'mvn clean install'
            }
            
        }
        stage('Bulding the DockerImage') {
            steps {
                sh 'echo "Bulding"'
                script {
                    dockerImage = docker.build(imageName + "${BUILD_NUMBER}")
                }
            }
        }
        stage('Publishing the Docker Image to Repo') {
            steps {
                sh 'echo "Publishing"'
                
            }
        }
    }
}
