pipeline{

    agent{ node {lable 'AGENT-1'}}
    

    option{

        timeout(time:1,unit:'HOURS')

    }
    environment {
        username = 'Saikumar'
    }

        stages{

            stage('install dependencies'){

                steps {
                    sh'''
                       install npm
                       echo " installed node js" 

                    '''
                }
            }
        stage('test')
        
        {
            steps{

                echo "unit testing"
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

//     post{

//         always{
//             success{
//                 echo "deployement success"
//             }
//             failure{
//                 echo "if deployement failed"
//             }
//         }

//     }







}