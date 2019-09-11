pipeline {
    agent any
    stages {
      stage ('Upload to AWS'){
          steps {
            sh 'echo "Hello World"'
            sh '''
                echo "Multiline shell steps works too"
                ls -lah
                '''
                withAWS(region:'us-west-2',credentials:'523856192541') {
                  s3Delete(bucket: 'jenkins-karim', path:'**/*')
                  s3Upload(bucket: 'jenkins-karim', workingDir:'build', includePathPattern:'**/*');
                  }
          }
      }
    }
  }
