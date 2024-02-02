pipeline {
    agent {
        label 'my-agent' // Replace 'my-agent' with the label or name of your Jenkins agent
    }
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/FenetShewarega/jenkinsrepo']]])
            }
        }
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/FenetShewarega/jenkinsrepo'
                sh 'python3 app.py'
            }
        }
        stage('Test') {
            steps {
                sh 'python3 -m pytest'
            }
        }
        stage('Deploy') {
            steps {
                // Add deployment steps here
                // For example, you can use 'kubectl' to deploy a Kubernetes application or 'ansible' for server deployments
                // Replace the placeholders with your actual deployment commands and configurations
                sh 'kubectl apply -f deployment.yaml' // Example Kubernetes deployment
            }
        }
    }
}
