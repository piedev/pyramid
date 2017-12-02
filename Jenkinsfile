pipeline {
  agent {
    dockerfile {
      filename 'Dockerfile.test'
    }
    
  }
  stages {
    stage('Retrieve repository') {
      steps {
        sh 'git clone https://github.com/piedev/pyramid.git -b feature/docker_image'
      }
    }
    stage('Build docker image') {
      steps {
        sh '''cd pyramid
docker build pyramid_test --file ./Dockerfile.test'''
      }
    }
  }
}