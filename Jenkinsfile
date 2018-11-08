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
    stage('Docker builder') {
      steps {
        dockerNode(dockerHost: 'tcp://10.31.2.182:2375', image: 'tomcat:latest') {
          sh '''env
ls -al'''
        }

        sh 'ls -al'
      }
    }
  }
}