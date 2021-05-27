pipeline
{
    environment
    {
        IMAGE = 'a7medayman6/jenkinstest'
        DOCKERHUB_CREDS = credentials('dockerhub')
    }
    agent any
    stages
    {
        stage('Build')
        {
            steps
            {       
                script
                {
                    
                    sh "docker build -t ${IMAGE} ."
                }          
            }
        }
        
        stage('Push')
        {
            steps
            {
                script
                {
                    
                    sh "docker login -u ${DOCKERHUB_CREDS_USR} -p ${DOCKERHUB_CREDS_PSW}"
                    sh "docker push ${IMAGE}:latest"       
                }
            }
        }
    }
}