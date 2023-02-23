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
        stage ('build image'){
            steps{
                docker('docker'){
                    sh 'docker build .'
                }
            }
        }
        stage ('login to docker hub'){
            steps{
                echo 'steps'
            }
        }
        stage ('push image'){
            steps{
                echo 'steps'
            }
        }
    }
}
