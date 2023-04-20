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

                    bat 'mvn verify DskipUnitTests'
                }
            }
        }
    }
}