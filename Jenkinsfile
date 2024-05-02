pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                echo "Building..."
            }
            post{
                always{
                    mail to: "s216137436@deakin.edu.au",
                    subject: "Build Status Email",
                    body: "Build log attached!"
                }
            }
        }
         stage("Test"){
            steps{
                echo "Unit tests"
                echo "integration tests"
            }
                post{
                success{
                    mail to: "s216137436@deakin.edu.au",
                    subject: "Test Status Email",
                    body: "Test was successful!"
                }
            }
        }
        }
    }



    
