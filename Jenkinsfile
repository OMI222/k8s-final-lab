pipeline {
    agent any
    stages {
        stage('Install Kubectl') {
            steps {
                sh '''
                # Скачиваем kubectl внутрь временной папки сборки
                curl -LO "https://dl.k8s.io/release/v1.27.3/bin/linux/amd64/kubectl"
                chmod +x ./kubectl
                '''
            }
        }
        stage('Check Cluster') {
            steps {
                // Запускаем kubectl, указывая на файл конфигурации, который мы подложили
                sh './kubectl get nodes'
            }
        }
    }
}
