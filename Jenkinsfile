pipeline {
    agent any
    stages {
        stage('Install Tools') {
            steps {
                script {
                    // Скачиваем kubectl прямо внутрь рабочей папки
                    sh 'curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"'
                    sh 'chmod +x ./kubectl'
                    
                    // Скачиваем Helm
                    sh 'curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3'
                    sh 'chmod 700 get_helm.sh && ./get_helm.sh --no-sudo'
                }
            }
        }
        stage('Check Connection') {
            steps {
                // Используем скачанный kubectl через ./
                sh './kubectl get nodes'
            }
        }
        stage('Check Helm') {
            steps {
                // Helm установится в текущую папку
                sh './helm list -A'
            }
        }
    }
}
