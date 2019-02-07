pipeline {
    agent { node { label 'swarm-build-agent' } }
    
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t tijmen34/portfoliowebsite:lts .'
            }
        }
        stage('Push Image') {
            steps {
                sh 'docker push tijmen34/portfoliowebsite:lts'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker service update --force portfolio-website'            
            }
        }
    }
}
