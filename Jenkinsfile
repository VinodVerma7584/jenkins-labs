node{
   stage('SCM Checkout'){
     git 'https://github.com/VinodVerma7584/jenkins-labs'
   }
   stage('Compile-Package'){
      // Get maven home path
      def mvnHome =  tool name: 'maven3', type: 'maven'   
      sh "${mvnHome}/bin/mvn package"
   }
   stage('Email Notification'){
      mail bcc: '', body: '''Hi Welcome to jenkins email alerts
      Thanks
      Hari''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'vedanteklabs@gmail.com'
   }
   stage('Slack Notification'){
       slackSend baseUrl: 'https://hooks.slack.com/services/',
       channel: '#jenkins',
       color: 'good', 
       message: 'Welcome to Jenkins, Slack!', 
       teamDomain: 'vedantek',
       tokenCredentialId: 'slack'
   }
}
