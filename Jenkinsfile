pipeline {
    agent any

    stages {
        stage('Build and Scan Code') {
            steps {
                script {
                    // SCM ve kod derleme işlemleri
                    checkout scm

                    // snyk komutunu çağır
                    bat 'C:\\Users\\selam\\AppData\\Roaming\\npm\\Snyk\\snyk code test'
                }
            }
        }

        // Diğer aşamalar buraya eklenir...
    }
}
