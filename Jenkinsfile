pipeline {
    agent any

    tools {
	nodejs 'Node Js 4.8.6'
       }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
		sh 'npm install'
		sh 'npm run test'
                sh 'npm run coverage'
            }
        }
        stage('Package') {
            steps {
                echo 'Deploying....'
		sh 'npm install'
		sh 'npm run package'
                archiveArtifacts artifacts: '**/distribution/*.zip', fingerprint: true
	     }
        }
    }
}
