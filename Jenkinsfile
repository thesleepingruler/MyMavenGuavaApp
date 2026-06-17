pipeline {
    agent any

    tools {
        maven 'maven'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/thesleepingruler/MyMavenGuavaApp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Create Source File') {
            steps {
                sh 'echo "This data will be copied!" > source.txt'
            }
        }

        stage('Run Application') {
            steps {
                sh 'mvn exec:java -Dexec.mainClass="com.example.App"'
            }
        }

        stage('Verify Output') {
            steps {
                sh 'cat destination.txt'
            }
        }
    }
}
