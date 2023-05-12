pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/main']],
        doGenerateSubmoduleConfigurations: false, extensions: [],
        submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/ankitrai0506/Jenkins-github.git']]])
      }
    }
    stage('Run Main.py') {
      steps {
        sh 'python main.py'
      }
    }
  }
}
