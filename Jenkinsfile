pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh 'echo "Hello World - This is Rajesh"'
        sh '''echo "Multi-line shell steps work too!"
ls -latr'''
      }
    }
    stage('Lint Html') {
      agent any
      steps {
        sh 'tidy -q -e *.html'
      }
    }
    stage('Upload to AWS') {
      steps {
        withAWS(credentials: 'aws-static') {
          s3Upload(bucket: 'jenkinsblueocean', file: 'index.html')
        }

      }
    }
  }
}