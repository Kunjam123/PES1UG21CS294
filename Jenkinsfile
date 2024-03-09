pipeline 
{
    agent any
        stages 
        {
            stage('Build') 
            {
                steps 
                {
                    sh'mvn clean install'
                    echo 'Build successful'
                }

            }

            stage('Test') 
            {
                steps 
                {
                    sh'mvn test'
                    echo 'Test successful'
                    post 
                    {
                        always
                        {
                            junit 'target/surefire-reports/*.xml'
                        }
                    }
                    //sh'./\output'
                }
            }

            stage('Deploy') 
            {
                steps 
                {
                    sh'mvn deploy'
                    echo 'deploy successful'
                }
            }

        }

    post
    {
        failure
        {
            error 'Pipeline failed'
        }
    }
}
