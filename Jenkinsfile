pipeline {
    agent { node { label 'slave01' } }

    stages {
        stage('Clone sources') {
            
            steps {
                    git branch: 'master',
                        url: 'https://github.com/sugandh1611/jenkins-maven-sample-app.git'
                    
                    sh 'pwd'
            }
            
    
        }
        
        stage ('Compile Stage') {

            steps {
                    sh 'mvn package'
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
