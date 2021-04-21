pipeline {
  agent {

    docker {
	image 'docker.io/vmdocker2022/build_agent'
     # image 'devcvs-srv01:5000/shop2-backend/jenkins-agent'
    }

  }

  stages {

    stage('Copy source with configs') {
      steps {
       echo 'Copy source with configs'
	   # git(url: 'http://cvs.tinkoff-dbs1.west.com/backendsbox/shop2.backend.git', branch: 'backend1-staging', poll: true, credentialsId: 'git')
       # sh 'ssh-keyscan -H devbuild-srv01 >> ~/.ssh/known_hosts'
       # sh 'scp jenkins@devbuild-srv01:/home/jenkins/build/configs/staging/gateway-api/application-business-config-defaults.yml gateway-api/src/main/resources/application-business-config-defaults.yml'
      }
    }
	
	}
	}