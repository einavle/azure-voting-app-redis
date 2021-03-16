pipeline {
    agent any

    stages {
        stage('verify docker') {
            steps {
                sh 'docker ps'
            }
        }
        stage('Push Container'){
            steps{
                echo "Workspace is $WORKSPACE"
                dir("$WORKSPACE/azure-vote"){
                    script {
                        docker.withRegistry('https://index.docker.io/v1/', 'dockerhub') {
                                def customImage = docker.build("einavl/jenkins-sample:${env.BUILD_ID}")
                                customImage.push()
                            }
                    }
                }
            }
        }
    }
}
