pipeline {
    agent {
        docker {
            image 'maven:3.9.0-eclipse-temurin-11' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('deploy') {
            steps {
                echo 'Deploying...'
                sh "mvn clean package deploy -Dusername=Rinca2 -Dpassword=6#Neliel@Rnc:any -Denvironment=sandbox -Dmule.version=4.4.0 -Dworkers=1 -Dworker.type=MICRO -Dapplication.name=devops-accounts -DmuleDeploy"
            }
        }
    }
}