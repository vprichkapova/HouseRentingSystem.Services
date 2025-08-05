pipeline {
    agent any

    tools {
        dotnet 'dotnet6' // Must match the name of the .NET SDK in Jenkins
    }

    stages {
        stage('Restore') {
            steps {
                sh 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet build --configuration Release --no-restore'
            }
        }

        stage('Test') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
