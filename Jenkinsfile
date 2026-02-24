pipeline {
    agent any
    stages {
        stage('Kubernetes Check') {
            steps {
                // Теперь эта команда сработает, так как мы скопировали kubectl и конфиг
                sh 'kubectl get nodes'
            }
        }
        stage('Cluster Info') {
            steps {
                sh 'kubectl cluster-info'
            }
        }
    }
}
