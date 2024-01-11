pipeline {
    agent any

    stages {
        stage('Build and Scan Code') {
            steps {
                script {
                    // SCM ve kod derleme işlemleri
                    checkout scm

                    // PATH değişkenini genişleterek 'cmd' komutunu ekleyin
                    bat '''
                        SET PATH=C:\\Windows\\System32;%PATH%
                        snyk code test
                    '''
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
