pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh "g++ -o PES1UG20CS274-1 sample.cpp"
            }
            post {
                always {
                    archiveArtifacts artifacts: 'PES1UG20CS274-1'
                }
            }
        }
        stage('Test') {
            steps {
                sh "./PES1UG20CS274-1"
            }
        }
        stage('Deploy') {
            steps {
                // Add deployment steps here, e.g. uploading to a server
            }
        }
    }
    post {
        always {
            script {
                if (currentBuild.result != 'SUCCESS') {
                    println('pipeline failed')
                }
            }
        }
    }
}
