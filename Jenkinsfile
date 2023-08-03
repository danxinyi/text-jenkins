pipeline {
  agent any
  stages {
    stage('pull') {
      agent any
      steps {
        git(url: 'git@github.com:danxinyi/alert_server.git', branch: 'master', changelog: true, credentialsId: '1')
      }
    }

    stage('build') {
      environment {
        version = 'test'
      }
      steps {
        sh 'docker build ./ -t alert_server:${version} -f dockerfile'
      }
    }

  }
}