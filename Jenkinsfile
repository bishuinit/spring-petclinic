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
  -Dsonar.host.url=http://localhost:9000 \\
  -Dsonar.projectKey=PetClinic8 \\
  -Dsonar.login=sqp_6efb59ee36a753ad7b93abf3b8d115842f00276c'''
      }
    }

  }
}