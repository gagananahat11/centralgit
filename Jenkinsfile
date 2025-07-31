pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                // Clone your GitHub repo (replace URL with your repo)
                git url: 'https://github.com/gagananahat11/centralgit.git'
            }
        }
        
        stage('Deploy to Nginx') {
            steps {
                // Copy index.html from repo to nginx html directory
                sh 'sudo cp index.html /usr/share/nginx/html/index.html'
            }
        }
    }
}
