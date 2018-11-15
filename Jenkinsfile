#!/usr/bin/env groovy
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
        withmaven(maven:'Maven test'){
           sh 'mvn compile' 
        }  
        /*echo 'Building...'
        sh 'mvn compile'*/
    }
    stage('Test'){
        sh 'mvn test'
        junit '**/target/*.xml'
        /*echo 'Testing...'   
        sh 'mvn test'*/
    }    
    stage('Deploy'){
        echo 'Deploying...'
        sh 'mvn package'
    }
}


