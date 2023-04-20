pipeline {
    agent any
    stages {
        stage('configuration') {
            steps {
                echo 'Reading configuration file'
                script {
                    envParams = readJSON(file: "./config.json").envParams
                }
            }
        }
        stage('deploy') {
            tools {
                maven 'Maven 3.8.1'
                jdk 'jdk11'
            }
            environment {
                ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
            }
            steps {
                echo 'Deploying...'
                sh 'mvn clean deploy -Denvironment=${envParams.environment} -DapplicationName=${envParams.applicationName} -Danypoint.username=${ANYPOINT_CREDENTIALS_USR} -Danypoint.password=${ANYPOINT_CREDENTIALS_PSW} -DmuleDeploy'
            }
        }
    }
}