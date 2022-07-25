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
    stage('Xbox | Debug') {
      parallel {
        stage('Xbox | Demo') {
          agent {
            node {
              label 'Aze'
            }

          }
          steps {
            build(job: 'Fractal_Space_Xbox_Debug', wait: true)
          }
        }

        stage('Series X | Demo') {
          agent {
            node {
              label 'Aze'
            }

          }
          steps {
            build(job: 'Fractal_Space_Scarlett_Debug', wait: true)
          }
        }

        stage('Store | Demo') {
          agent {
            node {
              label 'Aze'
            }

          }
          steps {
            build(job: 'Fractal_Space_GDK_Debug', wait: true)
          }
        }

      }
    }

  }
}
