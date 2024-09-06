pipeline {
    agent any

    tools {
        maven "maven"
    }

    stages {
        stage("SCM checkout") {
            steps {
               checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/djuric-ivan/jenkins-ci-cd']])
            }
        }
        stage("Build Process") {
            steps {
                script{
                    bat 'maven clean install'
                }
            }
        }
    }
}