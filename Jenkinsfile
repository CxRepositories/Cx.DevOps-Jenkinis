pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git(url: 'http://tfs2018app:8080/tfs/DefaultCollection/Enterprise/_git/Cx.RemediationIntelligence', branch: 'development', credentialsId: 'tfs')
      }
    }
    stage('Info') {
      steps {
        echo 'This is my test'
      }
    }
    stage('error') {
      steps {
        dockerNode(dockerHost: 'tcp://10.31.2.182', image: 'microsoft/dotnet') {
          echo '${env}'
        }

      }
    }
  }
}