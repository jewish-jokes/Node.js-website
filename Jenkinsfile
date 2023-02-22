pipeline{
    agent any

    stages {
        stage ('unit test'){
            steps{
                sh 'apt update'
                sh 'apt install npm'
                sh 'npm test'
            }
        }

        stage ('intergration test'){
            steps{
                sh 'npm test'
            }
        }
    }
}
