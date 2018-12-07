properties([pipelineTriggers([githubPush()])])
node('linux') {
    stage ("GetInstances") {
        sh "aws ec2 describe-instances --region us-east-1"
    }
    stage("CreateInstance") {
        sh "aws ec2 run-instances --image-id ami-0080e4c5bc078760e --count 1 --instance-type t2.micro --key-name EastVirginaNov --subnet-id subnet-08cd5e4f550ca6945 --security-group-ids sg-04271f12fb3b8276d --region us-east-1"
    }
    stage("UnitTests") {
        sh "ant -f test.xml -v"
    }
}
