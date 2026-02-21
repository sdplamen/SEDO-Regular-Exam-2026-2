pipeline {
    agent any

    stages {
        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Run the tests') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }

        stage('Test') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}