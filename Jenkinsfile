node {
    stage('SCM Checkout') {
        git 'https://github.com/soumyaraha/my-app'
     }
    stage('complile package') {
        sh 'mvn package'
     }
    stage('Email Notification') {
        mail bcc: '', body: 'Hello, I am learning Jenkins ', cc: '', from: '', replyTo: '', subject: 'Jenkins Test Mail', to: 'raha071278@gmail.com'     
    
    }
   }
