pipeline {
    agent { docker { image 'ruby' } }
    stages {
        stage('build') {
            steps {
                sh 'ruby --version'
                sh 'echo "Hello omega! This looks good so far!"'
            }
        }
    }
}
