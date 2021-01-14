pipeline {
    agent {
        docker {
            image 'golang:1.14'       
        }
    }
    environment {
        GO114MODULE = 'on'
        CGO_ENABLED = 0 
        GOPATH = "${JENKINS_HOME}/jobs/${JOB_NAME}/builds/${BUILD_ID}"
    }
    stages {        
        stage('Pre Test') {
            steps {
                echo 'Installing dependencies'
                sh 'go version'
                sh 'go get -u golang.org/x/lint/golint'
            }
        }
        
        stage('Build') {
            steps {
		checkout scm
                sh 'ls'
		echo 'Compiling and building'
                sh 'go build'
		sh 'ls'
                sh './script.sh'
            }
        }
    }
  
}
