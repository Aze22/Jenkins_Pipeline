pipeline {
  agent any
  stages {
    stage('Xbox') {
      parallel {
        stage('Xbox | Demo') {
          agent {
            node {
              label 'Aze'
            }

          }
          steps {
            build(job: 'Fractal_Space_Xbox', wait: true)
          }
        }

        stage('Series X | Demo') {
          agent {
            node {
              label 'Aze'
            }

          }
          steps {
            build(job: 'Fractal_Space_Scarlett', wait: true)
          }
        }

        stage('Store | Demo') {
          agent {
            node {
              label 'Aze'
            }

          }
          steps {
            build(job: 'Fractal_Space_GDK_Release', wait: true)
          }
        }

      }
    }

  }
}