pipeline {
  agent any
  stages {
    stage('clone') {
      parallel {
        stage('clone') {
          steps {
            dir(path: 'sunbird-devops') {
              git(url: 'https://github.com/project-sunbird/sunbird-devops', branch: 'release-1.12')
            }

          }
        }
        stage('sleep') {
          steps {
            sleep 10
          }
        }
      }
    }
    stage('show all files') {
      steps {
        sh """
              ls
              printenv
              echo ${env.env}
           """
      }
    }
  }
  environment {
    env = 'dev'
  }
}
