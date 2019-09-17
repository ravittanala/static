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
        s3Upload(file: 'index.html', bucket: 'jenkinsblueocean', includePathPattern: '**/*', pathStyleAccessEnabled: true, payloadSigningEnabled: true, acl: 'BucketOwnerFullControl')
      }
    }
  }
}