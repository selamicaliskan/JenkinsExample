pipeline {
    agent any

    stages {
        stage('Build and Scan Code') {
            steps {
                script {
                    // SCM ve kod derleme işlemleri
                    checkout scm

                    // PATH değişkenini kontrol et
                     bat 'SET PATH=%PATH%;C:\Users\selam\AppData\Roaming\npm'
                    
                    // snyk komutunu çağır
                    bat 'snyk code test'
                }
            }
        }

        // Diğer aşamalar buraya eklenir...
    }
}
