pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works here too"
                    ls -lah
                '''

                withAWS(region:'us-east-2',credentials:'Username: AKIA2HKW6PTTSVPNXCYS, Password: NZfx4agjND4Zx744Ij0r11o3lHaRa/48aG324pkV') {
                    s3Upload(file:'index.html', bucket:'jenkinspipelinesetup', path:'/Users/raphaelolams/Documents/projects/static/index.html')
                }
            }
        }
    }
}