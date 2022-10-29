pipeline {
  agent any
  stages {
    stage('clone') {
      steps {
        git(url: 'https://github.com/richmondamponsah/react-portfolio-website', branch: 'main')
      }
    }

    stage('build') {
      steps {
        sh '''whoami
date
echo $PATH
pwd
ls -la
npm install
npm build'''
      }
    }

    stage('publish') {
      steps {
        archiveArtifacts(artifacts: 'build/libs/*.war', fingerprint: true, onlyIfSuccessful: true)
      }
    }

  }
}