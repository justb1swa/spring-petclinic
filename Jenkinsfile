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
        sh ''' ./mvnw sonar:sonar \\ 
  -Dsonar.host.url=http://localhost:9000/ \\
  -Dsonar.projectKey=PetClinic \\
  -Dsonar.login=sqp_b1c131c18290b10bbc64afb074d7d5d9e1a1c7bc'''
      }
    }

  }
}