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

    stage('Xbox') {
      parallel {
        stage('Xbox | Demo') {
          agent any
          steps {
            build(job: 'Fractal_Space_Xbox', wait: true)
          }
        }

        stage('Series X | Demo') {
          agent {
            node {
              label 'Amy'
            }

          }
          steps {
            build(job: 'Fractal_Space_Scarlett', wait: true)
          }
        }

        stage('Store | Demo') {
          agent any
          steps {
            build(job: 'Fractal_Space_GDK_Release', wait: true)
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