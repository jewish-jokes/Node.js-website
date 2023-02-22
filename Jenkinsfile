pipeline{
    agent any

    stages {
        stage ('get checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/jewish-jokes/Node.js-website.git'
            }
        }

        stage ('unit test'){
            steps{
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