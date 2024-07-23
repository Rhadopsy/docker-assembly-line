pipeline {
  agent none

  stages {
    stage('maven') {
      agent {
        docker {
          image 'maven:3.6.3'
          args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
      }
      steps {
        sh "mvn -version"
        sh "java -version"
      }
    }

    stage('node') {
      agent {
        docker {
          image 'node:14'
          args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
      }
      steps {
        sh "node --version"
      }
    }

    stage('python') {
      agent {
        docker {
          image 'python:3.8'
          args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
      }
      steps {
        sh "python3 --version"
      }
    }

    stage('golang') {
      agent {
        docker {
          image 'golang:1.15'
          args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
      }
      steps {
        sh "go version"
      }
    }

    stage('gradle') {
      agent {
        docker {
          image 'gradle:6.7'
          args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
      }
      steps {
        sh "gradle --version"
      }
    }
  }
}
