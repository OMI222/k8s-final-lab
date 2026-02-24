pipeline {
    agent any
    stages {
        stage('Check Connection') {
            steps {
                sh 'kubectl get nodes'
            }
        }
        stage('Check Helm') {
            steps {
                sh 'helm list -A'
            }
        }
    }
}
