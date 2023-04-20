pipeline {
    agent any
    tools {
        maven 'Maven 3.8.1'
        jdk 'jdk11'
    }
    stages {
        stage('configuration') {
            steps {
                echo 'Reading configuration file'
                script {
                    envParams = readJSON(file: "./config.json").envParams
                }
            }
        }
        stage('test') {
            steps {
                echo 'Testing...'
                sh 'mvn -e clean test'
            }
        }
        stage('deploy') {
            environment {
                ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
            }
            steps {
                echo 'Deploying...'
                sh """mvn clean deploy -Denvironment=${envParams.environment} -DapplicationName=${envParams.applicationName} -Danypoint.username=${ANYPOINT_CREDENTIALS_USR} -Danypoint.password=${ANYPOINT_CREDENTIALS_PSW} -DmuleDeploy"""
            }
        }
    }
}