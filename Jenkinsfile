pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'docker build ./ -t alert_server:test -f dockerfile'
      }
    }

  }
}