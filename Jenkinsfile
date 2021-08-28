@Library('JenkinsSharedLibrary')_
pipeline {
    agent any
    tools {
        maven 'maven'
    }
    stages {
        stage("test") {
            steps {
                script {
                    buildJar()
                }
            }
        }
        stage("DockerLogin") {
            steps {
                script {
                    dockerLogin()
                }
            }
        }
        stage("DockerBuild") {
            steps {
                script {
                    buildImage()
                }
            }
        }
        stage("DockerPush") {
            steps {
                script {
                    dockerPush()
                }
            }
        }
        stage("Deploy") {
            steps {
                script {
                    deployApp()
                }
            }
        }
        
    }
}
