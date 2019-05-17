pipeline {
  agent any
  environment {
     registry = "registry.vitekey.net/vitekey/github-test-1"
     registryCredential = 'vitekey-registry'
  }
  stages {
    stage('Build') {
      steps {
        sh '''docker build -t registry.vitekey.net/vitekey/github-test-1:${BUILD_NUMBER} .

docker push registry.vitekey.net/vitekey/github-test-1:${BUILD_NUMBER}'''
      }
    }
  }
}
