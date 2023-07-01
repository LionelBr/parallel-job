pipeline{
    agent{
        label 'slave1'
    } 
    environment {
        token 'Quoe4ieL eaThooZ1 Eipe2ohk Irierah5 zeeTaib9 Zei1oogh OoneiSa1 Iiweoph6'
    }
    stages{
        stage('1-clone'){
            steps{
                sh 'cat /etc/passwd'
            }
        }
        stage('2-parallel-jobs'){
            parallel{
                stage('1-subjob1'){
                    agent {
                        label 'slave2'
                    }
                    steps{
                        sh 'lscpu'
                    }
                }
                stage('2-subjob2'){
                    when {
                        branch 'feature'
                    }
                    steps{
                        sh 'df -h'
                    }
                }
            }
        }
        stage('3-codetest'){
            agent {
                label 'slave1'
            }
            steps{
                sh 'free -m'
            }
        }
        stage('4-clossing'){
            agent{
                label 'slave2'
            }
            steps{
                echo "we are done "
            }
        }
    }
}