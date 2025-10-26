pipeline {
    agent any

    stages {
        stage('Build .NET Project') {
            when { branch 'main' }
            steps {
                bat 'dotnet build'
            }
        }

        stage('Run Unit and Integration Tests') {
            when { branch 'main' }
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }

    post {
        success {
            echo '✅ Build and tests completed successfully!'
        }
        failure {
            echo '❌ Build or tests failed.'
        }
    }
}
