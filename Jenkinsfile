pipeline {
  agent any

  stages {
      

    stage('1- build config-server') {
            steps {
                dir('config-server') {
                    sh 'mvn clean install -DskipTests'
                }
            }
        }

    stage('2- build employee-service') {
            steps {
                dir('employee-service') {
                    sh 'mvn clean install -DskipTests'
                }
            }
        }


    stage('3- build eureka-server') {
            steps {
                dir('eureka-server') {
                    sh 'mvn clean install -DskipTests'
                }
            }
        }
        
    stage("Deploy to preprod on matser") {
      when {
        // skip this stage unless on Master branch
        branch "master"
      }
      steps {
        echo "Deployimg to preprod env"
      }
    }      

    stage("Deploy to recette on stagging") {
      when {
        // skip this stage unless on Master branch
        branch "stagging"
      }
      steps {
        echo "Deployimg to recette env"
      }
    }    
  }
}
