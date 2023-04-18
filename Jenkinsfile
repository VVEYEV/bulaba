pipeline{

    agent any

    stages {

        stages{'Git Checkout'}{

            steps{
                
                script{

                    git branch: 'main', url: 'https://github.com/xyw3kLsi/bulaba.git'
                }
            }
        }
    }
}