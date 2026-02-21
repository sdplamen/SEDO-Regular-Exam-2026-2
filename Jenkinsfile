pipeline {
    agent any

    stages {
        stage('Restore dependencies') {
            when {
                expression{
                    return env.GIT_BRANCH=='origin/main'
                }
            }
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            when {
                expression{
                    return env.GIT_BRANCH=='origin/main'
                }
            }
            steps {
                bat 'dotnet build --no-restore --configuration Release'
            }
        }

        stage('Run the tests') {
            when {
                expression{
                    return env.GIT_BRANCH=='origin/main'
                }
            }
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}