pipeline {
  agent any
  stages {
    stage('Lint Html') {
      agent any
      steps {
        sh 'tidy -q -e *.html'
      }
    }
    stage('Build') {
      agent any
      steps {
        sh 'echo "Hello World"'
      }
    }
  }
}