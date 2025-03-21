pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }

        stage('Stocker l’artefact') {
            steps {
                sh '''
                mkdir -p /var/jenkins_home/artifacts
                cp -r dist/* /var/jenkins_home/artifacts/
                '''
            }
        }
    }

    post {
        success {
            echo "✅ Artefact stocké dans /var/jenkins_home/artifacts/"
        }
        failure {
            echo "❌ Échec du pipeline"
        }
    }
}
