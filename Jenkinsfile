pipeline {
  agent any
  stages {
    stage('buildStage') {
      steps {
        git(url: 'https://github.com/YaminiDockerUser/bosrepo2', branch: 'master', credentialsId: 'd71fe134-fbe1-4269-a81a-816d938e92f0')
        sh 'docker build -t yaminidockeruser/bosrepo2:latest .'
      }
    }

    stage('DevDeploy') {
      parallel {
        stage('DevDeploy') {
          steps {
            sh 'docker push yaminidockeruser/bosrepo2:latest'
          }
        }

        stage('DeployQA') {
          steps {
            echo 'QA Message'
          }
        }

      }
    }

  }
}