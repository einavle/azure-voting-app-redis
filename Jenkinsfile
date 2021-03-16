node {
    checkout scm
        echo "Workspace is $WORKSPACE"
        dir("$WORKSPACE/azure-vote"){
                docker.withRegistry('https://index.docker.io/v1/', 'dockerhub') {
                        def customImage = docker.build("einavl/jenkins-sample:${env.BUILD_ID}")
                        customImage.push()
                    }
                 }


}
