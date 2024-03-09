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
                    //build 'PES2UG21CS294-1'
                    //sh 'g++ main.cpp-o output'
                }

            }

            stage('Test') 
            {
                steps 
                {
                    sh'mvn test'
                    //sh'./\output'
                }
            }

            stage('Deploy') 
            {
                steps 
                {
                    sh'mvn deploy'
                    //echo 'deploy'
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
