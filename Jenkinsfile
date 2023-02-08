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
  -Dsonar.host.url=http://44.212.59.25:9000/ \\
  -Dsonar.projectKey=PetClinic8 \\
  -Dsonar.login=sqp_acebc55ef4a490cc8da17b8bbb8c749805a39352'''
      }
    }

  }
}