node {
        def majorVersion="1.0.${BUILD_NUMBER}"
	currentBuild.displayName = majorVersion

	//currentBuild.displayName = "2.0.${BUILD_NUMBER}"
	def GIT_COMMIT
  stage ('cloning the repository'){
	  
      def scm = git 'https://github.com/Kaushal604/Jpetstore-parker-4'
	  GIT_COMMIT = sh(returnStdout: true, script: "git rev-parse HEAD").trim()
	  echo "COMMITID ${GIT_COMMIT}"
	  //echo "BBBB ${scm}"
	  //GIT_COMMIT = scm.GIT_COMMIT
	   //echo "**** ${GIT_COMMIT}"
	  
  }
	
  
               
        	stage('SonarQube Analysis'){
		def mvnHome = tool name : 'Maven3.8.6', type:'maven'
		//def path = tool name: 'gradle-4.7', type: 'gradle'
		
		withSonarQubeEnv('sonarqube'){
			 			
		     sh	"mvn sonar:sonar -Dsonar.projectKey=JPetStore -Dsonar.host.url=http://13.232.179.123:9000/ -Dsonar.login=3c6c04e63d4e546f28413f3120dc578639526c6c"
		}
	 
	 }
	 }
	
	




