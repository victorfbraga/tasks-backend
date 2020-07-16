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
            stage ('Sonar Analysis') {
                environment{
                   scannerHome  = tool 'SONAR_SCANNER'
                }
                steps {
                      witchSonarQubeEnv('SONAR_LOCAL')  {
                        sh "${scannerHome}/bin/sonnar-scanner -e -Dsonar.projectKey=DeployBack -Dsonar.host.url=http://localhost:9000 -Dsonar.login=0e82bbdd3574aec9b6c59cb0e1322496437e0f2f -Dsonar.java.binaries=target -Dsonar.coverage.exclusions=**/.mvn/**,**/src/test/**,**/model/**,**Aplication.java" 
                      }

                    
                }
            }
    }

}
