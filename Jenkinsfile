pipeline {
    agent any
    stages{
        stage (git){
            steps {
                git branch: 'main', url: 'https://github.com/mahikilari/jaanu.git'
            }
        }
        stage (build){
            steps{
                sh 'mvn clean package'
            }
        }
        stage(deploy){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'likith', path: '', url: 'http://65.0.5.105:8080/')], contextPath: 'jjj', war: '**/*.war'
            }
        }
    }
}
