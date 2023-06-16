pipeline {
  agent any

  tools {nodejs "{your_nodejs_configured_tool_name}"}

  stages {
    stage('Install Postman CLI') {
      steps {
        sh 'powershell.exe -NoProfile -InputFormat None -ExecutionPolicy AllSigned -Command "[System.Net.ServicePointManager]::SecurityProtocol = 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://dl-cli.pstmn.io/install/win64.ps1'))"'
      }
    }

    stage('Postman CLI Login') {
      steps {
        sh 'postman login --with-api-key PMAK-648c89615228e90038ddea39-036756bca58c8ff834fb7d898f96b1d1e5'
      }
    }

    stage('Running collection') {
      steps {
        sh 'postman collection run "25044502-59e6f28f-4369-41b7-bea3-05a5a1345b7f" -e "25044502-ab323806-6d20-4e50-af62-3dae30d6fd11"'
      }
    }
  }
}
