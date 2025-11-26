pipeline {
    agent any
    stages {
        stage ('installmaven') {
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
        stage ('build') {
            steps {
                sh "mvn clean package"           
            }
        }
        stage ('deploy') {
            step {
                sh "sudo cp /var/lib/jenkins/workspace/hello-world-war/target/hello-world-war-1.0.0.war /opt/apache-tomcat-10.1.49/webapps/
            }
        }
    }
}
