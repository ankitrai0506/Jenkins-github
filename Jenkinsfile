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
    stage('Install Python'){
        steps {
            sh 'sudo apt-get update && sudo apt-get install -y python3'
        }
    }
    stage('Run Main.py') {
      steps {
        sh 'python main.py'
      }
    }
  }
}
