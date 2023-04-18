pipeline {
    agent any
    tools {
        maven 'Maven 3.9.1'
        jdk 'jdk11'
    }
    stages {
        stage('deploy') {
            environment {
                ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
            }
            steps {
                echo 'Deploying...'
                sh 'mvn deploy -P cloudhub -Dmule.version=3.9.0 -Danypoint.username=${ANYPOINT_CREDENTIALS_USR} -Danypoint.password=${ANYPOINT_CREDENTIALS_PSW}'
            }
        }
    }
}