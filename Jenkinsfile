pipeline {
    agent any
    environment {
        USER_CREDENTIALS = credentials('Personal_org')
        USER_KEY = credentials('key')
    }
    stages {
    	stage('Build Application') {
            steps {
                bat 'mvn clean install -Denv=dev -Dkey=%USER_KEY%'
            }
        }
        stage('Deploy Application') {
            steps {
                bat 'mvn package deploy -DmuleDeploy -Danypoint.username=%USER_CREDENTIALS_USR% -Danypoint.password=%USER_CREDENTIALS_PSW% -Denv=dev -Dkey=%USER_KEY%'
            }
        }
    }
}
