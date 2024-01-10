pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    // GitLab repo, main branch
                    git branch: 'main', url: 'https://gitlab.com/your-username/your-repo.git'
                }
            }
        }

        stage('Build') {
            steps {
                // Build steps
                script {
                    // Maven install
                    sh 'mvn clean install'
                }
            }
        }

        stage('Commit') {
            steps {
                // Commit changes to the repository
                script {
                    sh 'git add .'
                    sh 'git commit -m "Automated commit by Jenkins"'
                    sh 'git push origin main'
                }
            }
        }
    }

    post {
        success {
            echo 'Build successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
