pipeline {
    agent { node { label 'slave01' } }

    stages {
        stage('Clone sources') {
            
            steps {
                    git branch: '${git_branch}',
                        url: '${git_url}'
                    
                    sh 'pwd'
            }
            
    
        }
        
        stage ('Compile Stage') {

            steps {
                    sh '${compile}'
            }
        }

        stage ('Testing Stage') {

            steps {
                    sh '${test}'
            }
        }


        stage ('Deployment Stage') {
            steps {
                    sh '${deploy}'
            }
        }
    }
}
