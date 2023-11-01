pipeline {
    agent any
    tools {
        maven "M3"
    }
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/archibaldnewb/lbg-hello-world-maven.git'
            }
        }
        stage('Install') {
            steps {
            // Install the ReactJS dependencies
            sh "npm install"
            }
        }
        stage('Test') {
            steps {
          // Run the ReactJS tests
          sh "npm test"
            }
        }
        stage('Compile') {
            steps {
                sh "mvn clean compile"
            }
        }
        stage('Test') {
            steps {
                sh "mvn -Dmaven.compile.skip test"
            }
        }
        stage ('Package') {
            steps {
                sh "mvn -Dmaven.test.skip -Dmaven.compile.skip package"
            }
        }
    }
}