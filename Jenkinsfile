pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                echo "Building..."
            }
        }
            post{
                success{
                    mail to: "s216137436@deakin.edu.au",
                    subject: "Build Status Email",
                    body: "Build was successful!"
                }
            }
         stage('Test'){
            steps{
                echo "Unit tests"
                echo "integration tests"
            }
        }
        }
    }



    
