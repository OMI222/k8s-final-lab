pipeline {
    agent any
    stages {
        stage('Check Kubernetes') {
            steps {
                script {
                    // Мы пробуем выполнить команду через sudo, 
                    // так как у пользователя jenkins обычно нет прав на кубер
                    sh 'sudo kubectl get nodes'
                }
            }
        }
        stage('Check Helm') {
            steps {
                sh 'sudo helm list -A'
            }
        }
    }
}
