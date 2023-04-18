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
                echo $PATH
                sh "mvn clean package deploy -Dusername=Rinca2 -Dpassword=6#Neliel@Rnc:any -Denvironment=sandbox -Dmule.version=4.4.0 -Dworkers=1 -Dworker.type=MICRO -Dapplication.name=devops-accounts -DmuleDeploy"
            }
        }
    }
}