pipeline {
    agent any
    stages {
        stage('Lint HTML') {
            steps {
                tidy -q -e *.html
                }
            }
        stage('Upload to AWS') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
              withAWS(region:'us-east-2',credentials:'aws-static') {
                  s3Upload(bucket:"jenkins-cicd-pipeline-on-aws", includePathPattern:'**/*')
              
             
              }
            }
        }
    }
}
