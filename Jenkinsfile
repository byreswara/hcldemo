pipeline {
    agent any

    stages {
        stage('run ansible playbook') {
            steps {
                sshPublisher(publishers: [sshPublisherDesc(configName: 'ansible-server',
                transfers: [sshTransfer(cleanRemote: false,
                excludes: '',
                sourceFiles: '*.yaml'
                execCommand: 'ansible-playbook httpd.yaml',
                execTimeout: 120000,
                flatten: false,
                makeEmptyDirs: false,
                noDefaultExcludes: false,
                patternSeparator: '[, ]+',
                remoteDirectory: '',
                remoteDirectorySDF: false,
                removePrefix: '',
                )],
                usePromotionTimestamp: false,
                useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}
