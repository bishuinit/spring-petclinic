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
  -Dsonar.host.url=http://172.31.89.246:9000/ \\r \\
  -Dsonar.projectKey=SPetclinic \\
  -Dsonar.login=sqp_7ec0ce85868104bf17c928c50491d2dff69f7694'''
      }
    }

  }
}