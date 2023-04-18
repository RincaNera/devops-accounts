pipeline {
    agent any
    stages {
        stage('deploy') {
            steps {
                echo 'Deploying...'
                sh "C:/Users/Ban-K/Dev/apache-maven-3.9.1/bin/mvn clean package deploy -Dusername=Rinca2 -Dpassword=6#Neliel@Rnc:any -Denvironment=sandbox -Dmule.version=4.4.0 -Dworkers=1 -Dworker.type=MICRO -Dapplication.name=devops-accounts -DmuleDeploy"
            }
        }
    }
}