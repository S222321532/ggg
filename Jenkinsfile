pipeline{
    agent any 
    stages{
        stage("Buil"){
            echo "Building..."

        }
        post{
            always{
                mail to: "s222321532@deakin.edu.au",
                subject: "Buil Status Email",
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