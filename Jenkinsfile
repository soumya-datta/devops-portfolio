pipeline {
    agent any

    environment {
        KUBECONFIG = '/var/lib/jenkins/.kube/config'
    }

    stages {
        stage('Pull Code') {
            steps {
                echo "Downloading the latest portfolio code from GitHub..."
                checkout scm
                sh 'ls -la'
            }
        }
        stage('Test Docker Connection') {
            steps {
                echo "Checking if Jenkins has permission to use Docker..."
                sh 'docker --version'
            }
        }
        stage('Test Kubernetes Connection') {
            steps {
                echo "Checking if Jenkins has permission to talk to K3s..."
                sh 'k3s kubectl get nodes'
            }
        }
    }
}
