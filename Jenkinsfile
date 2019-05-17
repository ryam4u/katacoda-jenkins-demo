pipeline {
  agent any
  
  stages {    
    stage('Build') {
      steps {
        sh '''docker build -t registry.vitekey.net/vitekey/github-test-1:${BUILD_NUMBER} .'''
      }
    }
    stage('Push') {
      script {
        docker.withRegistry('https://registry.vitekey.net', 'vitekey-registry') {
           sh '''docker push registry.vitekey.net/vitekey/github-test-1:${BUILD_NUMBER}'''
        }
      }
    }
  }
  environment {
    registryCredential = 'vitekey-registry'
  }
}
