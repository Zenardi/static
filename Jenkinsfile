pipeline{
  agent any
  stages{
    
    stage('Lint HTML'){
      sh "tidy -q -e *.html"
    }
    
    stage('Upload to AWS'){
      steps {
        withAWS(region:'us-west-2') {
            s3Upload(file:'index.html', bucket:'zenardi-static-site', path:'index.html')
        }
      }
    }
  }
}
