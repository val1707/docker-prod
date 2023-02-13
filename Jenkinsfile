pipeline {
  environment {
    imagename = "val717/k8s-app"
    // registryCredential = 'docker-pass'
    dockerImage = ''
  }
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git branch: 'main', credentialsId: 'jenkins-pet', url: 'https://github.com/val1707/web-app.git'
 
      }
    }
    stage('Building docker image') {
      steps{
        script {
            sh 'docker build -t val717/k8s-app .'
        }
      }
    }
    // stage('Deploy Image') {
    //   steps{
    //     script {
    //       docker.withRegistry( '', registryCredential ) {
    //         dockerImage.push("$BUILD_NUMBER")
    //          dockerImage.push('latest')
    //       }
    //     }
    //   }
    // }
  }
}