pipeline {
  agent any
  tools { 
        maven 'Maven_3_2_5'  
    }
    environment {
        // Set JVM_OPTS without MaxPermSize
        JVM_OPTS = '-Xmx512m'
    }
   stages{

  stage('BuildingSourceCode'){
        steps{
        sh 'mvn clean install'
        }
  }
        stage('TestingSourceCode'){
            steps{
                sh 'mvn test'
        }
	}   
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=asecuritybuggyapp2_asecuritybuggyapp2 -Dsonar.organization=asecuritybuggyapp2 -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=9273c313f8157bdc12d049369d7e68ce394df3b4'
			}
       } 
  }
}
