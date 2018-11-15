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
        withMaven(maven:'Maven test'){
           sh 'mvn compile' 
        }  
        /*echo 'Building...'
        sh 'mvn compile'*/
    }
    stage('Test'){
        withMaven(maven:'Maven test'){
           sh 'mvn test' 
        }  
        //junit '**/target/*.xml'
        /*echo 'Testing...'   
        sh 'mvn test'*/
    }    
    stage('Deploy'){
        withMaven(maven:'Maven test'){
           sh 'mvn package' 
        }  
        
        /*echo 'Deploying...'
        sh 'mvn package'*/
    }
}


