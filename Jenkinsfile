pipeline {
    agent any

    environment {
        PATH = "C:\\Users\\selam\\AppData\\Roaming\\npm;%PATH%"
    }

    stages {
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
