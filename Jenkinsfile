pipeline {
    agent any

    stages {
        stage('Configure Helm Repo'){
            steps{
                sh """
                cd /var/lib/jenkins/workspace/jfrog-jenkins-integration
				helm repo add jenkins-helm https://mohib.jfrog.io/artifactory/api/helm/jenkins-helm --username mohibjehangir@gmail.com --password $token_jfrog
                """
            }
        }
        stage('Deploy helm chart to Repo') {
            steps {
                 sh """
                cd /var/lib/jenkins/workspace/jfrog-jenkins-integration
                curl -umohibjehangir@gmail.com:$token_jfrog -T /home/mohib/JFROG/kubernetes-logging-2.3.0.tgz "https://mohib.jfrog.io/artifactory/jenkins-helm/logging/kubernetes-logging-2.3.0.tgz"
                """
            }
        }
        stage('Resolve') {
            steps {
					sh """
					helm repo update
					
					"""
            }
			}
		}
	}
            
