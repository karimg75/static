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
                withAWS(region:'us-west-2',credentials:'4bd96054ae913eba5e42d1b00a8e3f9ff85fd4a4') {
                  s3Delete(bucket: 'jenkins-karim', path:'**/*')
                  s3Upload(bucket: 'jenkins-karim', workingDir:'build', includePathPattern:'**/*');
                  }
          }
      }
    }
  }
