pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Pull from Git') {
      steps {
        git(url: 'https://github.com/konstantinskorin/webappwar.git', branch: 'kskorin', credentialsId: 'GitHub', changelog: true, poll: true)
      }
    }
  }
}