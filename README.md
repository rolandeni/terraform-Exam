# terraform-Exam
contains IAC scripts to ochestrate jenkins then create a k8 cluster. also deploy sockshop to the cluster and deploy portfolio app to cluster.


Kubernetes Cluster with Jenkins.


How to create kubbernetes cluster with Jenkins 

Creating a Kubernetes cluster with Jenkins involves several steps. Here is an overview of the process:

Set up a Jenkins server: You need a Jenkins server to create a Kubernetes cluster. You can install Jenkins on a virtual machine, container or any other supported platform. in this project i installed jenkins with a bash script on AWS EC2 server using terraform. then displayed the public ip address using terraform output.

Install the Kubernetes plugin: The Kubernetes plugin allows Jenkins to interact with a Kubernetes cluster. You can install the plugin from the Jenkins plugin manager. manually visit Jenkins domain on a browser, click manage Jenkins, click manage plugins then install all recommend plugins and all required.

Configure the Kubernetes plugin: Once you have installed the Kubernetes plugin, you need to configure it to connect to your Kubernetes cluster. setup credentials to authenticate to the cluster, and other configuration parameters. such as AWS credentials and github credentials.

Create a Jenkins pipeline: A Jenkins pipeline is a script that defines the steps to be executed when a Jenkins job is run. You can create a pipeline to deploy your application to the Kubernetes cluster. The pipeline can include steps to build your application, create a Docker image, deploy the image to the cluster, and configure the Kubbernetes. for this step a Jenkins pipeline script is located in repo.

Test the pipeline: Once you have created the pipeline, you can test it to make sure it works as expected. You can run the pipeline manually or configure it to be triggered automatically when code changes are pushed to your source code repository.

using the Jenkins pipeline script, i also implemented monitoring tools such as Prometheus and grafana to monitor the state and health of the cluster.



