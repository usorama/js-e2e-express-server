pipeline {
    agent {label 'JDK-11-MVN'}
    parameters {
        choice(name: 'BRANCH_TO_BUILD', choices: ['main'], description: 'Branch to build')
    }
    stages {
        stage('get_git') {
            steps {
                git branch: "${params.BRANCH_TO_BUILD}", url: 'https://github.com/usorama/js-e2e-express-server.git'
            }
        }
        stage('build') {
            steps {
                sh 'npm install'
                sh 'npm run build'    
            }
        }
    }    
}