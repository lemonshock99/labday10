pipeline {
    agent any
    tools {
	go 'golang 1.15.9'
    }
    stages {
	stage('compile and test') {
	    agent {
		dockerfile {
		    filename 'Dockerfile.build'
		}
	    }
	    steps {
		sh 'cd hypernyms ; go build'
		sh './hypernyms/hypernyms'
		archiveArtifacts artifacts: 'hypernyms/hypernyms', fingerprint: true
	    }
	}
    }
}
