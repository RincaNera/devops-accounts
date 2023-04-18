pipeline {
    agent any
    stages {
        stage('deploy') {
            tools {
                maven 'Maven 3.8.6'
                jdk 'jdk11'
            }
            environment {
                ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
            }
            steps {
                echo 'Deploying...'
                sh 'printenv'
                sh 'mvn clean package deploy -Danypoint.username=${ANYPOINT_CREDENTIALS_USR} -Danypoint.password=${ANYPOINT_CREDENTIALS_PSW} -DmuleDeploy'
            }
        }
    }
}