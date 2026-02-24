pipeline {
    agent {
        docker {
            // Используем готовый образ, где всё уже установлено
            image 'dtzar/helm-kubectl:3.14'
        }
    }
    stages {
        stage('Validate Tools') {
            steps {
                // Здесь команды точно сработают, так как они вшиты в образ
                sh 'kubectl version --client'
                sh 'helm version'
            }
        }
        stage('Check Cluster') {
            steps {
                // Эта команда проверит связь с твоим кластером
                sh 'kubectl get nodes'
            }
        }
    }
}
