#!/usr/bin/groovy
import groovy.json.JsonOutput

pipeline {

    agent {
            docker {
                image = 'node:16-alpine'
            }
        }
    environment {
        test="testEnv"
    }

    stages {
        stage("STG 1"){
            steps {
                sh 'echo stg1'
            }
        }
        stage("STG 2"){
           parallel {
                stage('stg3') {
                    steps {
                        sh "echo test3"
                    }
                }
             }
        }
    }
    post {
        always {
sh "echo test3"
            }
    }
}
