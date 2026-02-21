pipeline {
    agent any
  
    triggers {
        githubPush()
    }

    stages {

        stage("Restore dep.") {
            when {
                branch 'main'
            }
            steps {
                bat "dotnet restore"
            }
        }

        stage("Build App") {
            when {
                branch 'main'
            }
            steps {
                bat "dotnet build --no-restore"
            }
        }

        stage("Run tests") {
            when {
                branch 'main'
            }
            steps {
                bat "dotnet test --no-build --verbosity normal"
            }
        }
    }
}
