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
  -Dsonar.host.url=http://localhost:9000/ \\
  -Dsonar.projectKey=PetClinic \\
  -Dsonar.login=sqp_6e8720e14eb584b28330b24c0bc94a9e0194f4b0'''
      }
    }

  }
}