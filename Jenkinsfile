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
    stage('list image') {
      steps {
        sh 'docker images'
      }
    }
    stage('Run the container'){
      steps{
        sh 'docker run --name my-nginx-container -d -p 8081:80 test_image'
      }
    }
    stage(list running container){
      steps{
        sh 'docker container ps'
        }
     }
  }
}
