pipeline {
    agent any

    stages {
        stage('Restore dependencies') {
            steps {
                ch 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                ch 'dotnet build --no-restore'
            }
        }

        stage('Run the tests') {
            steps {
                ch 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}