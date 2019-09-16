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
              withAWS(region:'us-west-2',credentials:'305115181912') {
                  s3Upload(bucket:"jenkins-cicd-pipeline-on-aws", path: "jenkins-cicd-pipeline-on-aws/", includePathPattern:'**/*');
            }
        }
    }
}
