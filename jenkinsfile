@Library('cicdlibrary')_

pipeline
{
    agent any
    stages
    {
        stage ('ContDownload_Master')
        {
            steps
            {
                script
                {
                    slpipeline.gitdownload("maven")
                }
            }
        }
        stage ('ContBuild_Master')
        {
            steps
            {
                script
                {
                    slpipeline.newbuild()
                }
            }
        }
        stage ('ContDeployment_Master')
        {
            steps
            {
                script
                {
                    slpipeline.newdeploy("DeclarativepipelineSLib","172.31.34.229","testapp")
                }
            }
        }
        stage ('ContTesting_Master')
        {
            steps
            {
                script
                {
                    slpipeline.gitdownload("Testingcode")
                    slpipeline.newtest("DeclarativepipelineSLib")
                }
            }
        }
        stage ('ContDelivery_Master')
        {
            steps
            {
                script
                {
                    slpipeline.newdeploy("DeclarativepipelineSLib","172.31.33.192","liveapp")
                }
            }
        }
    }
}
