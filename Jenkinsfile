pipeline {
    agent any
    tools {
        maven 'Maven 3.6.3'
        jdk 'jdk11'
    }
    stages {
        stage ('pull from git') {
            steps {
                git 'https://github.com/mfaruk/maven-pipeline.git'
            }
        }

        stage ('Build') {
            steps {
                //sh 'cd Maven-pipeline'
                sh 'mvn clean compile package'
                sh 'java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App'
            }
        }
    }
    post{
        always{
         echo 'I have finshed.'   
        }
        success{
         echo 'I have done successfully.'
        }
        failure{
         echo 'I failed.'   
        }
        
    }
}
