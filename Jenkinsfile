pipeline {
    agent any

    stages {
        stage('#1. Checkout') {
            steps {
               git branch: 'main', url: 'https://github.com/shivomm4887-coder/docker.git'
            }
        }
          stage('#2. Build Image'){
            steps{
              bat 'docker build -t myimg .'
            }
          }

          stage('#3. Stop old containers'){
            steps{
              bat 'docker stop mycont || exit 0'
              bat 'docker rm mycont || exit 0'
            }
          }

      stage('#4. Run Image - Containerise'){
            steps{
              bat 'docker run -d -p 4000:80 --name mycont myimg'
            }
          }
      
        }
}
