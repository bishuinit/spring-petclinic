pipeline {
  agent any
  stages {
    stage('Compile') {
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
        sh '''mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=PetClinic \\
  -Dsonar.host.url=http://172.31.89.246:9000 \\
  -Dsonar.login=sqp_4d0b7b9c8570997d02b679a107769112a662d66a'''
      }
    }

  }
}