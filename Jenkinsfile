pipeline {
  agent {
    dockerfile true
  }

  stages {
    stage('Checkout') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/main']],
        doGenerateSubmoduleConfigurations: false, extensions: [],
        submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/ankitrai0506/Jenkins-github.git']]])
      }
    }
    stage('Test') {
            steps {
                sh 'node --version'
                sh 'svn --version'
            }
        }
    }
}
