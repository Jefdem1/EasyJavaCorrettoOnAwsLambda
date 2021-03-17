# EasyJavaCorrettoOnAwsLambda
Deploy a Hello World function on AWS Lambda using Java Corretto 11

Launch an Amazon Linux 2 EC2 instance or similiar

sudo yum install -y git

sudo curl -L -o /etc/yum.repos.d/corretto.repo https://yum.corretto.aws/corretto.repo

sudo yum install -y java-11-amazon-corretto-devel

sudo wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo

sudo sed -i s/\$releasever/6/g /etc/yum.repos.d/epel-apache-maven.repo

sudo yum install -y apache-maven

git clone https://github.com/Jefdem1/EasyJavaCorrettoOnAwsLambda.git

mvn install

either winscp to the instance and download the demo-1.0.0.jar or run aws lambda command to upload directly

create lambda any name, runtime Java 11 (Corretto)

edit Handler

replace example.Hello::handleRequest with com.amazonaws.lambda.demo.LambdaFunctionHandler::handleRequest

