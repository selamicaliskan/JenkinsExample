pipeline {
    agent any
    tools {
        maven 'maven@latest' // Jenkins'ta tanımlanan Maven aracının adı
    }
    stages {
        stage('Build and Scan Code') {
            steps {
                script {
                    // SCM ve kod derleme işlemleri
                    checkout scm
                    bat 'mvn clean install'
                    snykSecurity(
                        snykInstallation: 'snyk@latest',
                        snykTokenId: 'selami',
                        targetFile: 'pom.xml',
                      // place other parameters here
                    )

                    // snyk komutunu çağır
                    bat 'C:\\Users\\selam\\AppData\\Roaming\\npm\\snyk code test'
                }
            }
        }

        // Diğer aşamalar buraya eklenir...
    }
}
