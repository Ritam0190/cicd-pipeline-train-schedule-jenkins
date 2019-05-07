pipeline {
  agent any 
  parameters {
      string(name: 'DEPLOY_ENV', defaultValue: 'TESTING', description: 'The target environment', )
      choice(name: 'User', choices: ['dev', 'test', 'master'])
  }
  stages {
    stage('Build') {
      steps {
        echo "Runnin build on ${params.DEPLOY_ENV} by ${params.User}"
        sh './gradlew build --no-daemon'
        archiveArtifacts artifacts: 'dist/trainSchedule.zip'
      }
    }
  }
}
