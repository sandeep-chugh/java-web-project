pipeline {
    agent any
    stages {
        stage("Build"){
            steps {
                sh 'mvn clean install'
            }
        }
        stage("Deply"){
            steps {
                deploy adapters: [tomcat7(credentialsId: 'c148899e-7977-4084-b1c7-2a089f4602e0', path: '', 
                url: 'http://ec2-54-158-180-37.compute-1.amazonaws.com:8080')], 
                contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }        
    }
}
