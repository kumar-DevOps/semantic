pipeline{
	agent any

    stages{
	        stage('branch name') {
	            steps{
		            echo "${env.BRANCH_NAME}"
		            sh '''
		                printenv
		            '''
	            }
            }
            stage('master'){
	            when {
	                branch "master"
	            }
	            steps{
		            echo "${env.BRANCH_NAME}"
		            echo "${BRANCH_NAME}"
			
			    sh '''
		                printenv
			            C:\Users\Admi\.dotnet\tools\dotnet-gitversion  \output buildserver
		            '''
	
		            echo "This is Master Branch Execution"
		            script {
			            def props = readProperties file: 'gitversion.properties'
			            env.GitVersion_SemVer = props.GitVersion_SemVer
			            env.GitVersion_FullSemVer = props.GitVersion_FullSemVer
			            env.GitVersion_BranchName = props.GitVersion_BranchName
			            env.GitVersion_AssemblySemVer = props.GitVersion_AssemblySemVer
			            env.GitVersion_MajorMinorPatch = props.GitVersion_MajorMinorPatch
			            env.GitVersion_sha = props.GitVersion_sha
			            echo env.GitVersion_SemVer
			            echo env.GitVersion_MajorMinorPatch
			            echo env.GitVersion_FullSemVer
		            }
	            }
            }

            stage('major'){
	            when {
	                branch "major/*"
	                }
	            steps{
		            echo "${env.BRANCH_NAME}"
		            echo "  ${BRANCH_NAME}"
    
	    	
		        echo "This is Master Branch Execution"
		            script {
			            def props = readProperties file: 'gitversion.properties'
			            env.GitVersion_SemVer = props.GitVersion_SemVer
			            env.GitVersion_FullSemVer = props.GitVersion_FullSemVer
			            env.GitVersion_BranchName = props.GitVersion_BranchName
			            env.GitVersion_AssemblySemVer = props.GitVersion_AssemblySemVer                                                                                                                                                                                                                                                                                                                                                                           nv.GitVersion_MajorMinorPatch = props.GitVersion_MajorMinorPatch
                        env.GitVersion_sha = props.GitVersion_sha
		    	        echo env.GitVersion_SemVer
		    	        echo env.GitVersion_MajorMinorPatch
		    	        echo env.GitVersion_FullSemVer
		            }
	            }
            }
        }
}
