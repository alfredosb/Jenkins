pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'mvn testing'
            }
        }
        stage('Desploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}
