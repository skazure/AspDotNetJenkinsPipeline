pipeline {

agent any

  environment {
    MSBUILD = "C:\\Program Files (x86)\\MSBuild\\14.0\\Bin\\MSBuild.exe"
    CONFIG = "Release"
    PLATFORM = '"Any CPU"'
	NUGETPATH = "C:\\software\\nuget.exe"
  }
  stages {
    stage('Build') {
      steps {
        bat "\"${NUGETPATH}\" restore AspDotNetJenkinsPipeline.sln"
        bat "\"${MSBUILD}\" AspDotNetJenkinsPipeline.sln /p:Configuration=${env.CONFIG};Platform=${env.PLATFORM} /maxcpucount:%NUMBER_OF_PROCESSORS% /nodeReuse:false /p:OutputPath=C:\\test"
      }
    }
  }
}