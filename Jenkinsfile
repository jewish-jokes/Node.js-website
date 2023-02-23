pipeline{
    agent any

    stages {
        stage ('unit test'){
            steps{
                nodejs('Node.js'){
                    sh 'npm install'
                    sh 'npm test'
                }
            }
        }

        stage ('intergration test'){
            steps {
                echo 'still working on it...'
            }
        }
    }
}
