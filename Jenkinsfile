pipeline{

    agent{ node {label 'AGENT-1'}}
    

    options{

        timeout(time:1, unit:'HOURS')

    }
    environment {
        username = 'Saikumar'
    }

        stages{

            stage('install dependencies'){

                steps {
                    sh 'npm install'
                    
                }
            }
        stage('test')
        
        {
            steps{

                echo "unit testing"
            }

        }

        // stage('sonar scanner')
        
        // {
        //     steps{
        //         //sh ' cd sonar-scanner.properties'
        //         sh 'ls -ltr'
        //         sh 'sonar-scanner'
            
        //     }


        // }
        stage(deploye)
        {
            steps{

                echo "deployement"
            }

        }

        stage('deploye artifacts')
        {
            steps{

                sh'''
                        ls -ltr
                        zip -r catalogue.zip ./* --exclude=.git --exclude=.zip
                '''
            }

        }

        stage('artifacts')
        {
            steps{
                nexusArtifactUploader(
                nexusVersion: 'nexus3',
                protocol: 'http',
                nexusUrl: '54.226.247.229:8081/',
                groupId: 'com.roboshop',
                version: '1.0.0',
                repository: 'catalogue',
                credentialsId: 'nexus-auth',
                artifacts: [
                    [artifactId: 'catalogue',
                    classifier: '',
                    file: 'catalogue.zip',
                    type: 'zip']
        ]
     )
            }
        }
        
        
//         stage(deploye)
//             when{

//                     environment name:'username',value:'Saikumar'

//             }
//             steps{

//                 echo "deploye success"
//                 error "if failed"
//                 printenv
//             }
        
//         }

    // post{

    //     always{
    //         success{
    //             echo "deployement success"
    //         }
    //         failure{
    //             echo "if deployement failed"
    //         }
    //     }

    // }







}
}