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
    stage('Build') {
      steps {
        tool 'Maven 3.6.2'
        sh '/opt/maven/maven/bin/mvn clean package'
      }
    }
    stage('Tests result') {
      steps {
        junit(testResults: 'target/surefire-reports/*.xml', healthScaleFactor: 1)
      }
    }
    stage('Archive Artifact') {
      steps {
        archiveArtifacts(artifacts: 'target/mywebapp.war', onlyIfSuccessful: true)
      }
    }
  }
}