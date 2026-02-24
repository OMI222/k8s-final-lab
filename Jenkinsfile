pipeline {
    agent any
    stages {
        stage('Check Connection') {
            steps {
                // Пробуем вызвать kubectl по полному пути
                sh '/usr/local/bin/kubectl get nodes || kubectl get nodes'
            }
        }
        stage('Check Helm') {
            steps {
                // Пробуем вызвать helm по полному пути
                sh '/usr/local/bin/helm list -A || helm list -A'
            }
        }
    }
}
