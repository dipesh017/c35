pipeline{
    agent {label 'worker'}
    options{
        buildDiscarder(logRotator(daysToKeepStr: '15'))
        disableConcurrentBuilds()
        timeout(time: 1, unit: 'MINUTES')
        retry(2)
    }
    parameters{
        string(name:'BRANCH', defaultValue: 'develop')
        choice(name: 'OPERATION', choices: ['A','S','M', 'D'])
        booleanParam(name: 'Doubts', defaultValue: true)
    }
    stages{
        stage("first"){
            steps{
                checkout scm
                sh "echo hello"
            }
        }
        stage("second"){
            steps{
                sh "echo hello"
            }           
        }
    }
}
