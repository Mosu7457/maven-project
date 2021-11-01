node{
	stage('SCM Checkout'){
		git 'https://github.com/Mosu7457/maven-project'
	}
	stage('Compile-Package'){
		// Get maven home path
		def mvnHome = tool name: 'maven-3', type: 'maven'
		sh "${mvnHome}/bin/mvn package"
	}
	stage('Email Notification'){
		mail bcc: '', body: '''HI welcome to Jenkins email alerts
		Thanks and Regards
		Mohsin Shaik''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'mail2mohsin10@gmail.com'
	}
	stage('Slack Notification'){
		slackSend baseUrl: 'https://hooks.slack.com/services/',
		channel: 'devops', color: 'good',
		message: 'Welcome to Jenkins, Slack!',
		tokenCredentialId: 'slack-demo',
		username: 'mosu7457'
	}
}
