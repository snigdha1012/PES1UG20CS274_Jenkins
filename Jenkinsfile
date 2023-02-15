pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'g++ -o PES1UG20CS274_task5 sample.cpp'
                build job: 'PES1UG20CS274-1'
            }
        }
        
        stage('Test') {
            steps {
                sh './PES1UG20CS274_task5'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deployment'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
