pipeline {
  agent {
    docker {
      image 'image \'node:lts-bullseye-slim\''
      args 'args \'-p 3000:3000\''
    }

  }
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
sh \'npm install\''''
      }
    }

    stage('publish') {
      steps {
        archiveArtifacts(artifacts: 'build/libs/*.war', fingerprint: true, onlyIfSuccessful: true)
      }
    }

  }
}