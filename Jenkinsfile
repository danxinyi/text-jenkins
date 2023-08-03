pipeline {
  agent any
  stages {
    stage('pull') {
      agent any
      environment {
        version = 'test'
      }
      steps {
        git(url: 'git@github.com:danxinyi/alert_server.git', branch: 'master', changelog: true, credentialsId: '1')
        sh 'docker build ./ -t alert_server:${version} -f dockerfile'
      }
    }

  }
}