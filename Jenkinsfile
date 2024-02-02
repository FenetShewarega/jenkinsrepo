pipeline {
    agent any
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
               sh 'cp *.py'
            }
        }
    }
}
