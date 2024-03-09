pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Compile .cpp file using a shell script
                    build 'PES1UG21CS294-1'
                    sh 'g++ -o output.exe main.cpp'
                    echo 'build successful'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Execute the compiled .cpp file and print output
                    sh './output.exe'
                    echo 'test successful'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy successful'
                // Your deployment steps here
            }
        }
    }

    post {
        always {
            // Display 'pipeline failed' in case of any errors
            echo 'Pipeline failed'
        }
    }
}
