pipeline {
    agent { 
        node {
            label 'docker-agent'
            }
      }
    triggers {
        pollSCM '* * * * *'
    }
stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh '''
                    echo "Compiling source code"
                    # Add your build commands here
                    # Example: mvn clean compile
                    # Example: npm install && npm run build
                    # Example: make build
                '''
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh '''
                    echo "Running unit tests"
                    # Add your test commands here
                    # Example: mvn test
                    # Example: npm test
                    # Example: pytest
                '''
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh '''
                    echo "Deploying to target environment"
                    # Add your deployment commands here
                    # Example: kubectl apply -f deployment.yaml
                    # Example: docker push myapp:latest
                    # Example: scp build/* user@server:/var/www/
                '''
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline completed'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
