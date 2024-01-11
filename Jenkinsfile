pipeline {
    agent any
    environment {
        SNYK_PATH = "C:\\Users\\selam\\AppData\\Roaming\\npm\\node_modules\\snyk" // Snyk'ın tam yolunu belirtin
    }
    stages {
        stage('Build and Scan Code') {
            steps {
                script {
                    // SCM ve kod derleme işlemleri
                    checkout scm
                    bat 'javac HelloWorld.java'

                    // Code scan işlemi (örneğin, Snyk)
                    bat 'snyk code test'
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Docker imajını oluşturma
                    bat 'docker build -t myapp:latest .'
                }
            }
        }

        stage('Scan Docker Image') {
            steps {
                script {
                    // Docker imajını tarayarak güvenlik kontrolü
                    bat 'snyk container test myapp:latest'
                }
            }
        }
    }
}
