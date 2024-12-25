pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t rohit630/service:v1 .'
            }
        }
        stage('Push') {
            steps {
                script {
                    // This step should not normally be used in your script. Consult the inline help for details.
                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh 'docker push rohit630/service:v1'
                    }
                }
            }
        }
    }
}
