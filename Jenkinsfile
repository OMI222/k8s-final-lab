pipeline {
    agent any
    stages {
        stage('Install Kubectl') {
            steps {
                sh '''
                curl -LO "https://dl.k8s.io/release/v1.27.3/bin/linux/amd64/kubectl"
                chmod +x ./kubectl
                '''
            }
        }
        stage('Check Cluster') {
            steps {
                // Добавляем флаг --insecure-skip-tls-verify, чтобы игнорировать смену IP
                sh './kubectl get nodes --insecure-skip-tls-verify'
            }
        }
    }
}
