pipeline {
  agent any
  stages {
    stage('CodeQL Scan') {
      environment {
        GITHUB_CREDS = credentials('pat-that-may-work')
      }
      steps {
        sh '''ls -lah
wget https://github.com/github/codeql-action/releases/download/codeql-bundle-20200826/codeql-runner-linux 
chmod +x codeql-runner-linux
ls -lah
commit_id=`git rev-parse HEAD`
refs_value=`git symbolic-ref HEAD`
./codeql-runner-linux init --repository rohitdemo/sru-codeql-js --github-url https://github.com --github-auth $GITHUB_CREDS_PSW
./codeql-runner-linux analyze --repository rohitdemo/sru-codeql-js --github-url https://github.com --github-auth $GITHUB_CREDS_PSW --commit $commit_id --ref $refs_value '''
      }
    }

  }
}