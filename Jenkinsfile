pipeline {
    agent any

    stages {
        stage("Fetch repository") {
            steps {
                    git 'https://github.com/chandra635313/javawar.git'
                }
            }	
            stage('Build') { 
            steps {
                 sh 'mvn -f pom.xml clean install'
            }
			}
            stage('Test') { 
            steps {
                  sh 'mvn -f pom.xml test'
                  
            }
        }
		stage("deploy"){
		stapes{
		deploy adapters: [tomcat9(credentialsId: 'tomcat_cred', path: '', url: 'http://44.204.128.209:8080/')], contextPath: null, war: '**/*.war'
		}
		}
		}
		}
