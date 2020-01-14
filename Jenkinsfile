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

                withAWS(region:'us-east-2', credentials: 'aws-static') {
                    s3Upload(file:'index.html', bucket:'jenkinspipelinesetup', path:'index.html')
                }

                sh 'echo "uploaded"'
            }
        }
    }
}