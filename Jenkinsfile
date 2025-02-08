pipeline {
    agent any  // Runs on any available Windows agent

    environment {
        DOTNET_VERSION = '6.0'  // Change to your required .NET version
        SOLUTION_FILE = 'SeleniumBasicExercise.sln'  // Change to your solution file
    }

    stages {
        stage('Checkout Code') {
            steps {
                script {
                    echo 'Checking out the code...'
                    checkout scm
                }
            }
        }

        stage('Restore Dependencies') {
            steps {
                script {
                    echo 'Restoring NuGet packages...'
                    bat "dotnet restore ${SOLUTION_FILE}"
                }
            }
        }

        stage('Build Solution') {
            steps {
                script {
                    echo 'Building the project...'
                    bat "dotnet build ${SOLUTION_FILE}"
                }
            }
        }

        stage('Run Tests for Project1') {
            steps {
                script {
                    echo 'Running tests from TestProject1...'
                    bat "dotnet test TestProject1/TestProject1.csproj"
                }
            }
        }

        stage('Run Tests for Project2') {
            steps {
                script {
                    echo 'Running tests from TestProject2...'
                    bat "dotnet test TestProject2/TestProject2.csproj"
                }
            }
        }

        stage('Run Tests for Project3') {
            steps {
                script {
                    echo 'Running tests from TestProject3...'
                    bat "dotnet test TestProject3/TestProject3.csproj"
                }
            }
        }
    }

    post {
        success {
            echo '✅ Build and Tests Passed Successfully!'
        }
        failure {
            echo '❌ Build or Tests Failed! Check logs.'
        }
    }
}