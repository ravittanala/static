pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh 'echo "Hello World - This is Rajesh"'
      }
    }
    stage('Lint Html') {
      agent any
      steps {
        sh 'tidy -q -e *.html'
      }
    }
    stage ('Upload to AWS') {
            steps {
                
                withAWS(credentials:'aws-static') {
                    // do something
                    s3Upload(bucket:"jenkinsblueocean", file:'index.html')
                }
            }
    }
  }
}
