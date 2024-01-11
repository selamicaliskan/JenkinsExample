pipeline {
    agent any

    stages {
        stage('Build and Scan Code') {
            steps {
                script {
                    // SCM ve kod derleme işlemleri
                    checkout scm
                    snykSecurity(
                      snykInstallation: 'snyk@latest',
                      snykTokenId: 'selami',
                        bat 'C:\\Users\\selam\\AppData\\Roaming\\npm\\snyk code test'
                      // place other parameters here
                    )

                    // snyk komutunu çağır
                    
                }
            }
        }

        // Diğer aşamalar buraya eklenir...
    }
}
