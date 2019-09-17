pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
              withAWS(region:'us-east-2',credentials:'aws-static') {
                  s3Upload(path: "http://jenkins-cicd-pipeline-on-aws.s3-website.us-east-2.amazonaws.com/", includePathPattern:'**/*')
              }
            }
        }
    }
}
