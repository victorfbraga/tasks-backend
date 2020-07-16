pipeline {
    agent any
    stages{
        stage ('Build Back End') {
                steps {
                    sh 'mvn clean package -DskipTests=true' 
                }
            }
        stage ('UNit Tests') {
                steps {
                    sh 'mvn test' 
                }
            }
    }

}