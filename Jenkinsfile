@Library('cicdlibrary')_

pipeline
{
    agent any
    stages
    {
        stage ('ContDownload_Loans')
        {
            steps
            {
                script
                {
                    slpipeline.gitdownload("maven")
                }
            }
        }
        stage ('ContBuild_Loans')
        {
            steps
            {
                script
                {
                    slpipeline.newbuild()
                }
            }
        }
     
     }
}
