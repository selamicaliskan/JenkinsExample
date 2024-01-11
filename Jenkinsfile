pipeline {
    agent any

    stages {
        stage('Check Environment') {
            steps {
                script {
                    bat 'set'
                }
            }
        }

        stage('Build and Scan Code') {
            steps {
                script {
                    // SCM ve kod derleme işlemleri
                    checkout scm

                    // PATH değişkenini kontrol et
                    bat 'echo %PATH%'
                    
                    // snyk komutunu çağır
                    bat 'snyk code test'
                }
            }
        }

        // Diğer aşamalar buraya eklenir...
    }
}
