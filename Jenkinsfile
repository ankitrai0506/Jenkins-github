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
    stage('build image'){
        steps {
            sh 'sudo su - jenkins'
            sh 'docker build -t test_image .'
        }
    }
    stage('Run Main.py') {
      steps {
        sh 'python3 main.py'
      }
    }
  }
}
