pipeline {
    agent any 
    stages{
        stage ("Code to clone"){
            steps{
                echo "cloning the code"
                git url:"https://github.com/anshtiwari9718/jenkins-project.git",branch:"main"
            }
        }
        stage ("Build"){
            steps{
                echo "building the image "
                sh 'docker build -t flask-jenkins-app .'
            }
        }
        stage ("Run docker container"){
            steps{
                echo "Container will run"
                sh ' docker rm -f flask_app || true'
                sh 'docker run -d -p 5000:5000 --name flask_app flask-jenkins-app'
                echo 'Container running sucessfully '
        }
    }
  }
}
    
