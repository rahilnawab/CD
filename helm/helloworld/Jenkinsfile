pipeline {
  agent any

  parameters {
  imageTag credentialId: 'dockerhub-pwd', defaultTag: '125', filter: '.*', image: 'rahilnawab/devops-integration', name: 'DOCKER_IMAGE', registry: 'https://registry-1.docker.io', tagOrder: 'DSC_VERSION'
}

  stages {
    stage('Pulling Docker Image') {
      steps {
        echo "Image = $DOCKER_IMAGE" 
        echo "Image Tag = $DOCKER_IMAGE_TAG" 
      }
    }
    stage('Checkout files'){
        steps{
          checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/rahilnawab/CD']]])
            }
        }

    stage('Deploying Selected Image in Helm locally'){
            steps {
              bat '''
                cd helm
                helm install demo helloworld --set image.tag=%DOCKER_IMAGE_TAG%
              '''
			}
		}
	}
}
