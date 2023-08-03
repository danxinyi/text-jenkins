pipeline {
  agent any
  stages {
    stage('pull') {
      steps {
        git(url: 'git@github.com:danxinyi/alert_server.git', branch: 'master', changelog: true, credentialsId: '1', poll: true)
        sh 'docker build ./ -t alert_server:tesr -f dockerfile'
      }
    }

  }
}