pipeline {
  agent any
  stages {
    stage('Start Server') {
      agent { label 'Aze' }
      steps {
        build(job: 'Startup_Server', wait: true)
      }
    }

    stage('Shutdown') {
      agent { label 'Aze' }
      steps {
         build(job: 'Shutdown_Server', wait: true)
      }
    }
  }
}
