/*pipeline {
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
            }
        }
        stage('Desploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}*/

node {
    checkout scm
    stage('Build'){
        echo 'Building...'
        sh 'mvn compile'
    }
    stage('Test'){
        echo 'Testing...'   
    }    
    stage('Deploy'){
        echo 'Deploying...'
    }
}


