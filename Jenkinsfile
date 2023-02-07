pipeline {
  agent any
  stages {
    stage('Compile') {
      agent {
        node {
          label 'test'
        }

      }
      steps {
        sh './mvnw clean compile'
      }
    }

    stage('Static Analysis') {
      agent any
      steps {
        sh '''./mvnw sonar:sonar \\ 
  -Dsonar.host.url=http://172.31.89.246:9000/ \\
  -Dsonar.projectKey=SPetclinic \\
  -Dsonar.login=sqp_23dabed5d80f08f063b1d3f37489493623f635ac'''
      }
    }

  }
}