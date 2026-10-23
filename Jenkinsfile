pipeline{
    agent{
        label "node"
    }
    stages{
        stage("Restore dependencies"){
            when {
                anyOf {
                    branch "main"
                    branch "develop"
                }
            }
            steps{
                bat "dotnet restore"
            }
        }
        stage("Build the project"){
            when {
                anyOf {
                    branch "main"
                    branch "develop"
                }
            }
            steps{
                bat "dotnet build --no-restore"
            }
        }
        stage("Run tests"){
            when {
                anyOf {
                    branch "main"
                    branch "develop"
                }
            }
            steps{
                bat "dotnet test --no-build --verbosity normal"
            }
        }
    }
}