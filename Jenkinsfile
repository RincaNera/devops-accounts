pipeline {
    agent any
    tools {
        maven 'Maven 3.9.1'
        jdk 'jdk11'
    }
    stages {
        stage('deploy') {
            steps {
                echo 'Deploying...'
                sh "mvn clean package"
            }
        }
    }
}