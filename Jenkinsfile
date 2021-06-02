pipeline{
    agent {
      label 'k8s-master'
    }
    stages{
        stage('deploy to kubernetes cluser'){
            steps{
                sshagent(['k8s-master']) {
                    script{
                        sh "kubectl run neonomics-app --image=sunil4356/neonomicsapp"
                        sleep 10
                        sh "kubectl expose pod/neonomics-app --name=neonomics-svc --type=NodePort --port 8080 "
                    }
                }
            }
        }
    }
}
