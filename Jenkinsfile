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
        sh ''' ./mvnw sonar:sonar \\ 
  -Dsonar.host.url=http://44.212.59.25:9000/ \\
  -Dsonar.projectKey=PetClinic \\
  -Dsonar.login=sqp_95ab57914a05c19eb69f39b483a1668594566308'''
      }
    }

  }
}