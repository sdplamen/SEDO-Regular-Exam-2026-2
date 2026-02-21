pipeline {
    agent any

    stages {
        stage('Restore dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet build --no-restore --configuration Release'
            }
        }

        stage('Run the tests') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}