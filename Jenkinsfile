/*This pipeline is specially designed for the games desing in unity 3D game engine. 
It is a simple pipeline that demonstrates the stages involved in the development and deployment of a Unity game.
*/
pipeline 
{
    agent any
        stages 
            {
                stage('Build') 
                    {
                        steps 
                            {
                                echo 'Task: Build the Unity project.'
                                echo 'Tool: Unity command line interface.'
                            }
                    }
            
                stage('Unit and Integration Tests') 
                    {
                        steps 
                            {
                                echo 'Task: Run unit tests and integration tests.'
                                echo 'Tool: Unity Test Runner.'
                            }   
                    }
            
                stage('Code Analysis') 
                    {
                        steps 
                            {
                                echo 'Task: Analyse the code to ensure it meets industry standards.'
                                echo 'Tool: SonarQube.'
                            }
                    }
                stage('Security Scan') 
                    {
                        steps 
                            {
                                echo 'Task: Perform a security scan on the code to identify any vulnerabilities.'
                                echo 'Tool: OWASP Dependency-Check.'
                            }
                        post 
                            {
                                success 
                                        {
                                            // emailext(
                                            mail to: 'mail2manish599@gmail.com',
                                            subject: "Jenkins Stage: '${env.STAGE_NAME}'",
                                            body: "The '${env.STAGE_NAME}' stage finished with status: ${currentBuild.result}",
                                            attachLog: true
                                            // )
                                        }

                                failure 
                                        {
                                            // emailext(
                                             mail to: 'mail2manish599@gmail.com',
                                            subject: "Jenkins Stage: '${env.STAGE_NAME}'",
                                            body: "The '${env.STAGE_NAME}' stage failed with status: ${currentBuild.result}",
                                            attachLog: true
                                            // )
                                        }
                            }
                    }
                stage('Deploy to Staging') 
                    {
                        steps 
                            {
                                echo 'Task: Deploy the game to a staging server or a test environment.'
                                echo 'Tool: AWS CLI or similar.'
                            }
                    }
                stage('Integration Tests on Staging') 
                    {
                        steps 
                            {
                                echo 'Task: Run integration tests on the staging environment.'
                                echo 'Tool: Unity Test Runner.'
                            }
                        post 
                            {
                                success 
                                        {
                                            // emailext(
                                           
                                            mail to: 'mail2manish599@gmail.com',
                                            subject: "Jenkins Stage: '${env.STAGE_NAME}'",
                                            body: "The '${env.STAGE_NAME}' stage finished with status: ${currentBuild.result}",
                                            attachLog: true
                                            // )
                                        }
                            

                                failure 
                                        {
                                            // emailext(
                                              
                                            mail to: 'mail2manish599@gmail.com',
                                            subject: "Jenkins Stage: '${env.STAGE_NAME}'",
                                            body: "The '${env.STAGE_NAME}' stage failed with status: ${currentBuild.result}",
                                            attachLog: true 
                                            // )
                                         }
                            }
                    }
                stage('Deploy to Production') 
                    {
                        steps 
                            {
                                echo 'Task: Deploy the game to a production server or publish it to a platform (e.g., Google Play Store, Apple App Store).'
                                echo 'Tool: Fastlane or similar.'
                            }
                    }
            }
}
