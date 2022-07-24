pipeline {
  agent any
  stages {
    stage('Start Server') {
      agent any
      steps {
        build(job: 'Startup_Server', wait: true)
        sleep 60
      }
    }

    stage('Win [DEBUG]') {
      parallel {
        stage('Win [DEBUG]') {
          agent any
          steps {
            build(job: 'Fractal_Space_x64_PreAlpha_Debug', wait: true)
          }
        }

        stage('Win [TEST]') {
          agent any
          steps {
            build(job: 'Fractal_Space_x64_PreAlpha_Test', wait: true)
          }
        }

        stage('Win | Demo [DEBUG]') {
          agent any
          steps {
            build(job: 'Fractal_Space_x64', wait: true)
          }
        }

      }
    }

    stage('Shutdown') {
      agent {
        node {
          label 'Aze'
        }

      }
      steps {
        build 'Shutdown_Server'
      }
    }

  }
}