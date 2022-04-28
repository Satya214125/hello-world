pipeline{
    agent  {label "chandu"}
    stages{
        stage("clone code"){
            steps{
                git 'https://github.com/sekharreddy0463/hello-world.git'
            }
        }
        stage("build"){
            steps{
                sh" mvn install"
            }
    
        }
        stage("test"){
            steps{
                sh"mvn test"
            }
        }
        
        stage("compile"){
            steps{
                sh "mvn compile"
            }
        }
        stage("validate"){
            steps{
                sh "mvn validate"
            }
        }
        stage("deploy"){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'tomcat_cred', path: '', url: 'http://44.204.128.209:8080/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
