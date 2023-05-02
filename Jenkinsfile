pipeline{

    agent any

    stages{

        stage('git checkout'){

            steps{
                
                script{

                    git branch: 'main', url: 'https://github.com/xyw3kLsi/bulaba.git'
                }
            }
        }
        stage('UNIT Testing'){

            steps{
                
                script{

                    bat 'mvn test'
                }
            }
        }
        stage('Integration testing'){

            steps{
                
                script{

                    bat 'mvn verify -DskipUnitTests'
                }
            }
        }
        stage('Maven Build'){

            steps{
                
                script{

                    bat 'mvn clean install'
                }
            }
        }
        stage('SonarQube analysis'){

            steps{
                
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-api-key') {    
                    bat 'mvn clean package sonar:sonar'
                 }
                }
            }
        }
        stage('Quality Gate status'){

            steps{
                
                script{

                    waitForQualityGate abortPipeline: false, credentialsId: 'sonar-api-key'
                }
            }
        }
    }
}