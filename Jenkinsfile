pipeline {
  agent any
  stages {
    stage('Compile') {
      agent any
      steps {
        sh './mvnw clean compile'
      }
    }

    stage('Static Analysis') {
      agent any
      steps {
        sh '''./mvnw sonar:sonar \\
  -Dsonar.projectKey=PetClinic8 \\
  -Dsonar.host.url=http://172.31.89.246:9000/ \\
  -Dsonar.login=sqp_acebc55ef4a490cc8da17b8bbb8c749805a39352'''
      }
    }

  }
}