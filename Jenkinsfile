pipeline{
    agent none
    stages{
        stage('Non_parallel_stage'){
            agent{
                label 'master'
            }
            steps{
                echo 'this will be executed first'
            }
            
        }
        
        stage('Run Test'){
            parallel{
                stage('test on window'){
                    agent {
                        label 'windows_node'
                    }
                    steps{
                        echo 'steps on windows agent'
                    }
                }
                
                stage('test on master'){
                    agent{
                        label 'master'
                    }
                    steps{
                        echo 'steps on master'
                    }
                }
                
            }
        }
    }
}
