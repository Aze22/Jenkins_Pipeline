pipeline {
  agent any
  stages {
    stage('Xbox | Test') {
      parallel {
        stage('Xbox | Demo') {
          agent {
            node {
              label 'Aze'
            }

          }
          steps {
            build(job: 'Fractal_Space_Xbox_Demo_Test', wait: true)
          }
        }

        stage('Series X | Demo') {
          agent {
            node {
              label 'Aze'
            }

          }
          steps {
            build(job: 'Fractal_Space_Scarlett_Demo_Test', wait: true)
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