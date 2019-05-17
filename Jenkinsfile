pipeline {
  agent {
    node {
      label 'docker-agent'
    }

  }
  stages {
    stage('Push') {
      steps {
        script {
          docker.withRegistry('https://registry.vitekey.net', 'vitekey-registry') {
            dockerImage = docker.build('registry.vitekey.net/vitekey/github-test-1:${BUILD_NUMBER}')
            dockerImage.push()
          }
        }

      }
    }
  }
  environment {
    registryCredential = 'vitekey-registry'
    dockerImage = ''
  }
}