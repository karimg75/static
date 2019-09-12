pipeline {
    agent any
    stages {
        stage ('Say Hello - Build init') {
            steps {
                
                sh 'echo "Hello World "'
                
                sh '''
                  echo "Multi-line works too!"
                  ls -lrtha
                '''
            }
        }
        stage ('Lint HTML') {
            steps {
                sh "tidy -q -e index.html"
            }
        }
        stage ('Upload to AWS') {
            steps {
                
                withAWS(region:'us-west-2',credentials:'aws-static') {
                    // do something
                    s3Upload(bucket:"jenkins-karim", file:'index.html')
                }
            }
        }        
    }
}
