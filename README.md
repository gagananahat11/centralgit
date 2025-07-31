pipeline {
    agent any

    stages {
        stage('Create HTML') {
            steps {
                script {
                    writeFile file: 'index.html', text: '''
                    <!DOCTYPE html>
                    <html>
                    <head>
                        <title>My Nginx Page</title>
                    </head>
                    <body>
                        <h1>Hello from Jenkins without Docker!</h1>
                    </body>
                    </html>
                    '''
                }
            }
        }
        
        stage('Deploy to Nginx') {
            steps {
                // Copy index.html to nginx html directory
                sh 'sudo cp index.html /usr/share/nginx/html/index.html'
            }
        }
    }
}

