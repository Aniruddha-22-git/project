
pipeline {
agent {
label {
		label "built-in"
		customWorkspace "/mnt/project-myapp"
		
		}
		}
		
	stages {
		
		/*stage ('CLEAN_OLD_M2') {
			
			steps {
				sh "rm -rf /home/saccount/.m2/repository"
				
			}
			
		}
	
		stage ('MAVEN_BUILD') {
		
			steps {
						
						sh "mvn clean package"
			
			}
			
		
		}
		
		stage ('COPY_WAR_TO_Server'){
		
				steps {
						
						sh "scp -r target/LoginWebApp.war saccount@10.0.2.51:/data/project/wars"

						}
				
				}
	
	
	
	}*/
		stage ('project-file'){
			steps {
				sh "cd /mnt/project-myapp"
				sh "mvn clean install"
				sh "cp -r /target/LoginWebApp.war /mnt/server/apache-tomcat-9.0.93/webapps"
				sh "/mnt/server/apache-tomcat-9.0.93/bin/ ./startup.sh"
			}
		}
		
}
}
