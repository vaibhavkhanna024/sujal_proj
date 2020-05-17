pipeline {
    agent any
    environment {
        USER_CREDENTIALS = credentials('AnypointExchangeID')
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
        stage('Test Application By Hitting API') {
            steps {
                bat '"C:\\Users\\Sujal Anand\\AppData\\Roaming\\npm\\"newman run "C:\\Users\\Sujal Anand\\Desktop\\CI-CD-Newman\\CI-CD-GetFlights-Jenkins.postman_collection.json" --disable-unicode'
                }
        }
    }
}