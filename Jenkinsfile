pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Pull from Git') {
      parallel {
        stage('Pull from Git') {
          steps {
            git(url: 'https://github.com/konstantinskorin/webappwar.git', branch: 'kskorin', credentialsId: 'GitHub', changelog: true, poll: true)
          }
        }
        stage('') {
          steps {
            git(url: 'https://github.com/konstantinskorin/webappwar.git', branch: 'master', changelog: true, credentialsId: 'GitHub', poll: true)
          }
        }
      }
    }
  }
}