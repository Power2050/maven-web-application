pipeline{
    agent any
    tools {
        maven "maven3.6.0"
    }
    stages {
        stage('1GetCode'){
            steps{
                sh "echo 'cloning the latest application version' "
                //git "https://github.com/Power2050/maven-web-application"
                git branch: 'feature', credentialsId: 'gitHubCredentials', url: 'https://github.com/Power2050/maven-web-application'
            }
    }
    //stage('2Testing'){}
    stage('3Test&Build'){
        steps{
            sh "echo 'running JUnit-test-cases' "
            sh "echo 'testing must pass to create artifacts' "
            sh "mvn clean package"
        }
    }
    /*
    stage('4codeQuality'){
        steps{
            sh "echo 'performing CodeQualityAnalysis' "
            sh "mvn sonar:sonar"
        }
    }
	stage('5uploadNexus'){
	    steps{
	        sh "mvn deploy"
	    }
	}
	
	//stage('6deploy2UAT'){}
	//stage('7approvalGate'){}
	stage('8deploy2Prod'){
	    steps{
	        deploy adapters: [tomcat9(credentialsId: 'tomcat-credentials', path: '', url: 'http://172.31.81.159:8080/')], contextPath: null, war: 'target/*war'
	    }
	}
	/*
	stage('9emailNotification'){}
	*/
	}


    post {
	    always{
	    emailext body: '''Hey guys

Please check build status.

Thanks 
JD from Landmark
555-555-5555''', recipientProviders: [buildUser(), developers()], subject: 'success', to: 'joshdow222@gmail.com'
	}
	success{
	    emailext body: '''Hey guys

Good job build and deployment is successful

Thanks 
JD from Landmark
555-555-5555''', recipientProviders: [buildUser(), developers()], subject: 'success', to: 'joshdow222@gmail.com'
	}
	failure{
	    emailext body: '''Hey guys

Build failed. Please resolve issues.

Thanks 
JD from Landmark
555-555-5555''', recipientProviders: [buildUser(), developers()], subject: 'success', to: 'joshdow222@gmail.com'
	}
    }
    */
    }

