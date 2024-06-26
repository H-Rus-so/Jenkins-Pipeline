pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                echo """
                    Building...
                    During the Build stage, Maven is commonly used for its extensive dependency management 
                    and ability to package applications into formats like JAR or WAR files. 
                    Gradle is another chosen option, especially noted for its versatility with multiple languages 
                    and a more flexible, powerful scripting language compared to Maven's XML.
                    """
            }
            post {
                always {
                    mail to: "h.subacc24@gmail.com",
                    subject: "Build Status Email with normal mail",
                    body: "CHANGED GITHUB - AUTO UPDATE"
                }
            }
        }
        stage("Test") {
            steps {
                echo """
                    Unit tests running...
                    Integration tests running...
                    In the Unit and Integration Tests stage, JUnit and TestNG are commonly used for Java testing, 
                    with JUnit focusing on unit tests and TestNG on handling more complex test environments. 
                    Mockito complements these by providing mocking tools essential for isolated testing. 
                    Tools like Postman and SoapUI are also highly used, particularly for their user-friendly interfaces that facilitate API testing.
                    """
                    }
           post {
                always {
                    emailext(
                        to: 'h.subacc24@gmail.com',
                        subject: "Test Notification: ${JOB_NAME}-Build# ${BUILD_NUMBER} ${currentBuild.result}",
                        body: "${currentBuild.result}: ${BUILD_URL}",
                        attachLog: true,
                        compressLog: true,
                        replyTo: 'h.subacc24@gmail.com'
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo """
                    Checking the quality of the code...
                    The Code Analysis stage could rely on SonarQube as a tool to ensure the code meets industry standards for quality and security. 
                    ESLint and StyleCop extend these capabilities to JavaScript and C# projects, respectively, helping enforce specific coding standards 
                    and identifying potential issues early.
                    """
            }
        }
        stage('Security Scan') {
            steps {
                echo """
                    Performing security scan...
                    For the Security Scan stage, OWASP ZAP is integrated into Jenkins pipelines for dynamic security scanning. 
                    Fortify and Checkmarx may add value with their static analysis capabilities, 
                    identifying security vulnerabilities at the source code level to uphold application security.
                    """
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo """
                    Deploying to Staging...
                    In the Deploy to Staging stage, Jenkins is used extensively to automate deployment processes, with Docker 
                    enhancing this step by containerising applications for consistent deployment across environments.
                    """
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo """
                    Running integrations tests on staging environment...
                    During the Integration Tests on Staging stage, 
                    Selenium is used for its robust automated testing capabilities in simulated production environments. 
                    Cypress offers an alternative with its unique architecture that can run tests faster and with fewer issues, 
                    providing a more reliable testing experience.
                    """
            }
        }
        stage('Deploy to Production') {
            steps {
                echo """
                    Deploying to production stage...
                    Deploy to Production stage sees the use of Jenkins for automation, 
                    with Kubernetes playing a crucial role in managing and scaling containerised applications across clusters, 
                    ensuring smooth and resilient deployments.
                    """
            }
        }
    }
}
