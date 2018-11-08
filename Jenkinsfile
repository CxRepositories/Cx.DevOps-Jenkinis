pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git(url: 'http://tfs2018app:8080/tfs/DefaultCollection/Enterprise/_git/Cx.RemediationIntelligence', branch: 'development')
      }
    }
    stage('Build RemediationIntelligence') {
      steps {
        timeout(time: 10) {
          mail(subject: 'Build OK', body: 'Build OK', to: 'yuri.shterenberg@checkmarx.com')
        }

      }
    }
    stage('Info') {
      steps {
        echo 'This is my test'
      }
    }
    stage('error') {
      steps {
        dockerNode(dockerHost: '10.31.2.182', image: 'microsoft/dotnet') {
          echo '${env}'
        }

      }
    }
  }
}