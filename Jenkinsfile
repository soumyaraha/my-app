node {
    stage('SCM Checkout') {
        git 'https://github.com/soumyaraha/my-app'
     }
    stage('complile package') {
        sh 'mvn package'
     }
    stage('Deploy to Tomcat') {
        sshagent(['tomcat-dev']) {
        sh 'scp -o StrictHostKeyChecking=no target/*.war appuser@192.168.43.208/opt/tomcat10/webapps'
    }
    }
    stage('Email Notification') {
        mail bcc: '', body: 'Hello, I am learning Jenkins ', cc: '', from: '', replyTo: '', subject: 'Jenkins Test Mail', to: 'raha071278@gmail.com'     
     }
    stage('Slack Notification') {
        slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'jenkins-pipeline-demo', color: 'good', message: 'Hello Jenkins! Slack Notification', teamDomain: 'soumya-workspacegroup', tokenCredentialId: 'slack-demo'
    }
   }
