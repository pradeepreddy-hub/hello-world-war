pipeline {
    agent none
    stages {
        parallel {
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
        }
        stage ('deploy') {
            steps {
                sh "sudo cp /home/slave1/workspace/hello-world-war-pipeline/target/hello-world-war-1.0.1.war /opt/apache-tomcat-10.1.49/webapps/"
            }
        }
    }
}
