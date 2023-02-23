pipeline{
    agent any

    stages {
        stage ('unit test'){
            steps{
                nodejs('Node.js'){
                    sh 'npm test'
                }
            }
        }

        stage ('intergration test'){
            steps{
                sh 'npm test'
            }
        }
    }
}
