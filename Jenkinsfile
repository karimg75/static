pipeline {
    agent any
    stages {
      stage ('Upload to AWS'){
          steps {
            sh 'echo "Hello WorldK"'
            sh '''
                echo "Multiline shell steps works too"
                ls -lah
                '''
          }
      }
    }
  }
}
