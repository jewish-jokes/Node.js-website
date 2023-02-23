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
        stage ('push image'){
            docker.withRegistry('https://registry.example.com', 'credentials-id') {

                def customImage = docker.build("my-image:${env.BUILD_ID}")
                customImage.push()
            }
            
        }
    }
}

post {
    always{
        sh 'docker logout'
    }
}
