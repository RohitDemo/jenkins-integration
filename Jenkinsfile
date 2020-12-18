pipeline {
  agent any
  stages {
    stage('CodeQL Scan') {
      environment {
        GITHUB_CREDS = credentials('pat-that-may-work')
      }
      steps {
        sh '''
pwd
ls -lah
mkdir codeql-bundle/
cp -r /home/ubuntu/codeql-bundle/ codeql-bundle/
ls -lah
commit_id=`git rev-parse HEAD`
echo " COMMIT ID is $commit_id"
refs_value=`git symbolic-ref HEAD`
echo "REF is $refs_value"
      }
    }

  }
}