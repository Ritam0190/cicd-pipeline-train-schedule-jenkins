pipeline {
  agent any 
  options([
    parameters([
      string(name: 'DEPLOY_ENV', defaultValue: 'TESTING', description: 'The target environment', ),
      choice(name: 'User', choices: ['TESTING\nSTAGING\nPRODUCTION'])
    ])
  ])
  stages {
    stage('Build') {
      steps {
      echo "Runnin build on $DEPLOY_ENV by $User"
      sh './gradelw build --no-daemon'
      archiveArtifacts artifacts: 'dist/trainSchedule.zip'
      }
    }
  }
}
