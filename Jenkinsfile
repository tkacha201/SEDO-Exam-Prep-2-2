pipeline{
    agent any

    stages{
        stage("Restore .NET Packages"){
            when {
                branch 'main'
            }
            steps{
                bat 'dotnet restore' //For Windows
            }
        }
        stage("Build .NET Project"){
            when {
                branch 'main'
            }
            steps{
                bat 'dotnet build --no-restore' //For Windows
            }
        }
         stage("Run Unit and Integration Tests"){
            when {
                branch 'main'
            }
            steps{
                bat 'dotnet test --no-build --verbosity normal' //For Windows
            }
        }
    }
}