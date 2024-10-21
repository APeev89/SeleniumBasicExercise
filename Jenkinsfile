pipeline {
    agent any
    
    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scr
            }
        }

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

        stage('Run IU Tests Project 1') {
            steps {
                bat 'dotnet test TestProject1/TestProject1.csproj --no-build --verbosity normal'
            }
        }

        stage('Run IU Tests Project 2') {
            steps {
                bat 'dotnet test TestProject2/TestProject2.csproj --no-build --verbosity normal'
            }
        }

        stage('Run IU Tests Project 3') {
            steps {
                bat 'dotnet test TestProject3/TestProject3.csproj --no-build --verbosity normal'
            }
        }
    }
}
