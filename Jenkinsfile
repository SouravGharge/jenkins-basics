pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh "docker pull jenkins/jenkins"  // Docker pulls jenkins image
            }
        }

        stage('Scan with Grype') {
            steps {
                sh '''
                    echo "[*] Running Grype scan..."
                    grype jenkins/jenkins  // Grype jenkins scan
                '''
            }
        }
    }
}
