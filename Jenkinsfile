pipeline{
    agent any

    environment{
        DOCKERHUB_CREDENTIALS = credentials('docker.hub-credentials')
    }

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
                sh 'docker build . -t jewishjokes/my_image:lts'
            }
        }
        stage ('login to docker hub'){
            steps{
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage ('push image'){
            steps{
                sh 'docker push jewishjokes/my_image:lts'
            }
        }
    }
}

post {
    always{
        sh 'docker logout'
    }
}
