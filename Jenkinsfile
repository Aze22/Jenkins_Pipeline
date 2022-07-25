pipeline {
  agent {
    node {
      label 'Aze'
    }

  }
  stages {
    stage('Start Server') {
      agent any
      steps {
        build(job: 'Startup_Server', wait: true)
        sleep 60
      }
    }

    stage('Windows | Debug') {
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

  }
}