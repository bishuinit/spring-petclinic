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
      agent {
        node {
          label 'test'
        }

      }
      steps {
        sh '''./mvnw sonar:sonar \\
  -Dsonar.host.url=http://172.31.89.246:9000/ \\
  -Dsonar.projectKey=PetClinic \\
  -Dsonar.login=sqp_e8c2b543521f81e473ccc05ef271051548b5f20e'''
      }
    }

  }
}