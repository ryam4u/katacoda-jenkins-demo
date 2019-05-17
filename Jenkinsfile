pipeline {
  agent any
  environment {
    registryCredential = 'vitekey-registry'
    dockerImage = ''
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
 
}
