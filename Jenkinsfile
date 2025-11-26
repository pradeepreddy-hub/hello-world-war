pipeline {
    agent any
    stages {
        stage ('Installmaven') {
            steps {
            sh "sudo apt update"
            sh "sudo apt install maven -y"
          }
        }
        stage('checkout') {
            steps {
                sh "rm -rf hello-world-war"
              sh "git clone https://github.com/pradeepreddy-hub/hello-world-war"
            }
        }
    }
}
