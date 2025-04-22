pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/SouravGharge/jenkins-basics.git'  // My repository
            }
        }

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
