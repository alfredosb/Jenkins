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
        junit '**/target/*.xml'
        /*echo 'Testing...'   
        sh 'mvn test'*/
    }    
    stage('Deploy'){
        withMaven(maven:'Maven test'){
           sh 'mvn package' 
        }  
        
        git add target
        git commit -am 'OK'
        
        /*echo 'Deploying...'
        sh 'mvn package'*/
   }
}

/*node {
    try {
        stage('Test') {
            sh 'echo "Fallo!"; exit 1'
        }
        echo 'Se ejecuta si exito'
    } catch (e) {
        echo 'Se ejecuta si fallo'
        throw e
    } finally {
        def currentResult = currentBuild.result ?: 'SUCCESS'
        if (currentResult == 'UNSTABLE') {
            echo 'Se ejecuta si unstable'
        }

        def previousResult = currentBuild.previousBuild?.result
        if (previousResult != null && previousResult != currentResult) {
            echo 'Se ejecuta si hay cambio de estado'
        }

        echo 'Se ejecuta siempre'
    }
}*/


