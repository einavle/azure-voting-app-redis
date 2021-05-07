node('master'){
    stage('on master'){
      sh 'echo hi I am master'
    }
}
node('slave'){
    stage('git'){
        git branch: 'scripted', url: 'https://github.com/einavle/azure-voting-app-redis.git'
    }
    stage('stage 1'){
        sh 'echo in stage 1 on slave'
    }
}
