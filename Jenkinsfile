pipeline {
  agent any
  tools {
      go 'gotest'
  }
  environment {
      GO111MODULE='on'
  }
  
  stages {
    stage('Test') {
      steps {
        git 'https://github.com/databinaries001/ci-cd-demo.git'
        sh 'go test ./...'
      }
    }
    stage('Build') {
        steps {
        git 'https://github.com/databinaries001/ci-cd-demo.git'
        sh 'go build .'
        }
    }
    stage('Run') {
        steps {
            sh 'cd /var/lib/jenkins/workspace/full-cicd-go && go-webapp-sample &'
        }
    }

  }
}


----*** Build a Full CI/CD Pipeline ***----

>>> New Item -> Pipeline ->

>> Build Triggers - GitHub hook trigger for GITScm polling (Check it)

>> Pipeline -> Pipeline script from SCM
SCM - Git
  Repository URL - https://github.com/smartynoman9595/ci-cd-demo.git

>> Credentials - Add - Username and password (Give uname and pass of Github)

Save

>>Now go under github and update jenkins file with below code and commit on github itself
pipeline {
  agent any
  tools {
      go 'gotest'
  }
  environment {
      GO111MODULE='on'
  }
  
  stages {
    stage('Test') {
      steps {
        git 'https://github.com/smartynoman9595/ci-cd-demo.git'
        sh 'go test ./...'
      }
    }
    stage('Build') {
        steps {
        git 'https://github.com/smartynoman9595/ci-cd-demo.git'
        sh 'go build .'
        }
    }
    stage('Run') {
        steps {
            sh 'cd /var/lib/jenkins/workspace/full-pipeline && go-webapp-sample &'
        }
    }

  }
}
