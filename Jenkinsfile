pipeline {
  agent any
  stages {
    stage('Lint Html') {
      agent any
      steps {
        sh 'tidy -q -e *.html'
      }
    }
    stage('Upload to AWS') {
      agent any
      steps {
        withAWS(region:'us-east-2',credentials:'aws-static')
          s3Upload(bucket: 'jenkinsblueocean', includePathPattern:'**/*');
      }
    }
  }
}
