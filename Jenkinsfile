pipeline {
  agent any

  stages {
      
    stage('build') {
            steps {
                sh 'mvn clean install'
            }
        }

    stage("One") {
      steps {
        echo "Hello"
      }
    }
    stage("Evaluate Master") {
      when {
        // skip this stage unless on Master branch
        branch "master"
      }
      steps {
        echo "World"
        echo "Heal it"
      }
    }
  }
}
