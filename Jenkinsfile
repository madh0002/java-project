properties([pipelineTriggers([githubPush()])])
node('linux') {
    stage("UnitTests") {
        sh 'ant -f -buildfile test.xml -v'
    }
}
