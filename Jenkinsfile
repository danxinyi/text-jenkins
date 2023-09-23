pipeline {
  agent none
  stages {
    stage('build') {
      agent any
      steps {
        git(url: 'git@github.com:danxinyi/alert_server.git', branch: 'master', changelog: true, credentialsId: '1')
        sh 'docker build ./ -t alert_server:build -f dockerfile-cicd'
        sh 'docker tag alert_server:build sg.ayi21sui.online:5000/alert_server:${version}'
        sh 'docker push sg.ayi21sui.online:5000/alert_server:${version}'
        sh 'docker rmi alert_server:build'
      }
    }

  }
  environment {
    version = 'v6.7'
  }
}