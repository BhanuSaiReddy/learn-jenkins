pipeline {
  agent none

  stages {
    stage('Back-end') {
      agent {
        docker {
          image 'ubuntu:latest'  // Use a base image
          args '--user=root'     // Run as root to install packages
        }
      }
      steps {
        echo "Installing Maven inside the container"
        sh '''
          apt-get update
          apt-get install -y maven openjdk-11-jdk
          mvn --version
        '''
      }
    }

    stage('Front-end') {
      agent {
        docker {
          image 'node:16-alpine'
          args '--user=root'
        }
      }
      steps {
        echo "Installing Node.js inside the container"
        sh '''
          apk add --no-cache nodejs npm
          node --version
          npm --version
        '''
      }
    }
  }
}
