pipeline {
    agent { node { label 'slave01' } }

    stages {
        stage('Clone sources') {
            
            steps {
                    git branch: 'master',
                        url: 'https://github.com/sugandh1611/jenkins-maven-sample-app.git'
                        
                    pwd()
            }
        }
        
        stage ('Testing dir '){
            steps {
                dir('/home/vagrant'){
                    sh 'pwd'
                    sh 'touch sp-test'
                }
            }
        
        }
        stage ('Compile Stage') {

            steps {
                dir('/home/jenkins/ /home/jenkins/ /home/jenkins/workspace/maven-app'){
                    sh 'pwd'
                    sh 'mvn package'
                }    
            }
        }

        stage ('Testing Stage') {

            steps {
                    sh 'mvn test'
            }
        }


        stage ('Deployment Stage') {
            steps {
                    sh 'java -cp target/*.jar helloworld.HelloWorld'
            }
        }
    }
}
