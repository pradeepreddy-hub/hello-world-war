pipeline {
    // agent { label 'java' }
    agent any
    parameters {
        string(name: 'mcd1', defaultValue: '', description: 'Enter your name')
        choice(name: 'mcd2', choices: ['install', 'package', 'compile'], description: 'select the choice')
    }
    stages {
        stage ('hello-world-war') {
            parallel {
        stage('checkout') {
            agent { label 'java' }
            steps {
                sh "rm -rf hello-world-war"
              sh "git clone https://github.com/pradeepreddy-hub/hello-world-war"
            }
        }
        stage ('build') {
            agent { label 'java' }
            steps {
                sh "mvn $mcd1 $mcd2"           
            }
        }
        stage ('deploy') {
            agent { label 'java' }
            steps {
                sh "sudo cp /home/slave1/workspace/hello-world-war-pipeline/target/hello-world-war-1.0.1.war /opt/apache-tomcat-10.1.49/webapps/"
            }
        }
        }
    }
}
}
