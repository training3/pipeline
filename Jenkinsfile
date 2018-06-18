node{

    repositoryName = "WAMGateway"



try {

    stage('Clone') {

            checkout scm

	        echo "${repositoryName}"

    }}}

/*

    stage('Restore Dependency'){

		dir('WAMBuild') {

                    bat '''rem ensure the registry setting is present

                        set "var=%~dp0"

                        regedit.exe -s %var%msbuild-enable-out-of-proc.reg



                        rem removing the \\packages folder (if present).

                        rmdir ..\\packages /s /y



                        rem restore nuget

                        dir

			 nuget.exe restore ..\\wamgateway.sln

                        '''

                        }}



    stage('Build') {

        dir('WAMBuild') {

            bat "\"${tool 'msbuild-default'}/msbuild\" wam.msbuild /t:Clean,Build /p:Configuration=Desktop"



            bat "\"${tool 'msbuild-default'}/msbuild\" wam.msbuild /t:BuildSetup /p:Configuration=Desktop"



            bat "\"${tool 'msbuild-default'}/msbuild\" wam.msbuild /t:Clean,Build /p:Configuration=Citrix"



            bat "\"${tool 'msbuild-default'}/msbuild\" wam.msbuild /t:CitrixBuildSetup /p:Configuration=Citrix"

          }}



    stage ('Nunit test') {

        dir('WAMBuild') {

            bat "\"${tool 'msbuild-default'}/msbuild\" wam.msbuild /t:Clean,BuildTestProject /p:Configuration=Release"

	   }}



	stage('SonarQube analysis') {

		def scannerHome = tool 'SonarQube';

        withSonarQubeEnv('sonarQube') {

		    bat "${scannerHome}/bin/sonar-scanner"

			}}



    stage('Upload artifacts') {

		def server = Artifactory.server ('artifacts')

		def uploadSpec = """{

			"files": [

			{

			    "pattern": "WAMGateway-Citrix/Citrix/*.msi",

				"target": "nuget-local/WAMGateway/dev/${env.BUILD_NUMBER}/"

				    },

			{

				"pattern": "WAMGatewaySetup/Desktop/*.msi",

				"target": "nuget-local/WAMGateway/dev/${env.BUILD_NUMBER}/"

				    }

				         ]

			        }"""



		def buildInfo1 = server.upload(uploadSpec)

        server.publishBuildInfo(buildInfo1)

			       }

                }

        

    // catching error

    catch(error) {

        notifyBuild('FAILED')

        throw error;

    }

}
*/
