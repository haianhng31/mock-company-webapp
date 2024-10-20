pipeline {
  agent any 

  stages {
    stage("Build") {
      steps {
        // TODO: Run the build process
        sh './gradlew assemble'
      }
    }

    stage("Test") {
      steps {
        sh './gradlew test'
      }
    }
  }

  post {
      success {
          archiveArtifacts artifacts: '**/build/libs/*.jar', allowEmptyArchive: true
      }
      failure {
          echo 'Build or tests failed. Please check the logs for details.'
      }
  }
}
