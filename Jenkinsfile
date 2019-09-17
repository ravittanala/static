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
    stage('Upload to AWS') {
      agent any
      steps {
        withAWS(credentials:'aws-static')
            s3Upload(file:'index.html',bucket: 'jenkinsblueocean', includePathPattern:'**/*')
      }
    }
  }
}
