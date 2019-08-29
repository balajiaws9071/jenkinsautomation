pipeline {
    agent any
    stages {
     stage('SCM Checkout') {
         steps {
         echo "Checking out from the source Repository"
         git url: 'https://github.com/balajiaws9071/jenkinsautomation'
     }
     }
     stage('Compile stage') {
         steps {
         echo "compiling the source"
         withMaven(maven: 'Maven_3.6.0') {
            sh 'mvn compile'
}
     }
     }
     stage('Test stage') {
         steps {
         echo "Testing the source"
         withMaven(maven: 'Maven_3.6.0') {
            sh 'mvn test'
}
     }
     }
     stage('Package stage') {
         steps {
         echo "Package the source"
         withMaven(maven: 'Maven_3.6.0') {
            sh 'mvn package'
}
     }
     }
     stage('Deploy stage') {
         steps {
         echo "Deploy the source"
         deploy adapters: [tomcat8(credentialsId: 'e87d00fd-9e54-4ffc-80fa-ec03b6c9a984', path: '', url: 'http://54.236.55.153:9090/')], contextPath: 'mvn-hello-world', war: 'target/*.war'
     }
     }
    }
}
