pipeline{
    agent any 
    stages{
        stage("Build"){
            echo "Building..."

        }
        post{
            always{
                mail to: "s222321532@deakin.edu.au",
                subject: "Build Status Email",
                body: "Build log attached"
            }
        }
    }

    stage("Test"){
        steps{
            echo "Testing..."
        }
    }
    stage("Deploy"){
        steps{
            echo "Deploying..."
        }
    }
}
