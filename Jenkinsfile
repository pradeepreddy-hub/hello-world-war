pipeline {
    // agent { label 'java' }
    agent any
    parameters {
        string(name: 'mcd1', defaultValue: '', description: 'Enter your name')
        booleanParam(name: 'Boolean', defaultValue: true, description: 'Enable or disable')
        choice(name: 'mcd2', choices: ['install', 'package', 'compile'], description: 'select the choice')
    }
    stages {
        stage('checkout') {
            // agent { label 'java' }
            steps {
                withCredentials([usernamePassword( credentialsId: '069fddf1-c2cf-4262-9172-5bb4cfbd94c7', usernameVariable: 'admin', passwordVariable: 'admin_password'
)])
                sh "rm -rf hello-world-war"
              sh "git clone https://github.com/pradeepreddy-hub/hello-world-war"
            }
        }
        stage ('build') {
            steps {
                sh "mvn $mcd1 $mcd2"           
            }
        }
        stage ('deploy') {
            steps {
                sh "sudo cp /home/slave1/workspace/hello-world-war-pipeline/target/hello-world-war-1.0.1.war /opt/apache-tomcat-10.1.49/webapps/"
            }
        }
        
    }
}


