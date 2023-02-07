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
        sh '''  ./mvnw sonar:sonar \\
  -Dsonar.host.url=http://localhost:9000/ \\
  -Dsonar.projectKey=PetClinic \\
  -Dsonar.login=sqp_12484e55a11381f95097a274569eb696ef44b3ce'''
      }
    }

  }
}