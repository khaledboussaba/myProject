pipeline {
    
    agent any
    tools {
        maven 'maven3'
    }
    
    stages {
        stage('checkout') {
            steps {
                sh 'echo "=-- Checkout Stage --=--"'
                git 'https://github.com/khaledboussaba/myProject.git'
            }
        }
        stage('build') {
            steps {
                sh 'echo "=-- Build Stage --=--"'
                sh 'mvn clean compile'
            }
        }
        stage('test') {
            steps {
                sh 'echo "=-- Test Stage --=--"'
                sh 'mvn test'
            }
            post {
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                }
            }
        }
        stage('package') {  
            steps {
                sh 'echo "=-- Package Stage --=--"'
                sh 'mvn clean package'
            }
        }
    }
    
}
