pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                echo "Building..."
            }
            post{
                success{
                    mail to: "s216137436@deakin.edu.au",
                    subject: "Build Status Email",
                    body: "Build was successful!"
                }
            }
                    stage('Build'){
            steps{
                echo "Fetch the source code from $DIRECTORY_PATH"
                echo "Compile code and generate any necessary artifacts"
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
}


    
