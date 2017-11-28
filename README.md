In this page I would show how to deploy applications on your local machine test the application and move the application to the cloud. I would be using Docker for start, then move to kubernetes, on the local machine, then to both google cloud and AWS
Kubernetes Clusters on local Machine

Introduction
Before going deep into kubernetes, to better appreciate kubernetes it is essential to understand dockers and how dockers work. This will give you better insights into kubernetes.
Dockers serves as a ship which can house numerous containers. in deploying a highly scalable application over a cluster of VM machines or availabilty zones (it must be noted that Kubernets cannot spinng accross regions.This process is complex using dockers, this is where kubernetes comes into play. please in understanding Dockers technology please refer to the link I attach to this page (......). This is very essetial so as to understand the procedures I would be showing on this page.

Later on on this Tutorials, we would run complex clusters, and show various ways to prove test your application before pushing it production. I would start with a simple example. Then move on to a very complex example of applications, where if you follow me you would learn a great deal for your self or for your company.

In simple terms, kubernetes coordinates a highly available cluster of computers, VMs, Systems, applications, that are connected together to work as a single unit. Hence u can have many computer clusters connected to work as one unit using Kubernetes. Salient points about Kubernetes:
Deploying a containerized application over a cluster of different machines.
Highly scalable
Automates distribution and scheduling of application containers efficiently.
The Master controls/monitors the clusters, the nodes run applications.

You can deploy Kubernetes on AWS and GCE easily. Look into the pages
AWS - (......)
GCE - (.......)

To deploy Kubernetes on your local Machine: You will need to configure the machine.
Install a hypervisor (This makes to create a virtualization environments In my case I am using Ubuntu, and I install VirtualBox) there are many option to use:
For Linux install VirtualBox or KVM
For windows install VirtualBOX or Hyper-V
For OS X, install xhype driver, VirtualBox, or VmwareFusion
Install Kubectl: This is simply the command line tool used handle all operations of kubernetes on clusters in the cloud or in the local machine There are various ways to do it: I would only refer to the means that is convinient for me and I hope for redears as well.

If you are using Linux:
this is the link to the latest release with the command: curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
Enable the kubernete release to be executable: chmod +x ./kubectl
Move the binary into your PATH: sudo mv ./kubectl /usr/local/bin/kubectl
If you are using MacOS:
this is the link to the latest release with the command: curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/darwin/amd64/kubectl
Enable the kubernete release to be executable: chmod +x ./kubectl
Move the binary into your PATH: sudo mv ./kubectl /usr/local/bin/kubectl
If you are using windows:
and you have curl installed: use this command to install: curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.8.0/bin/windows/amd64/kubectl.exe
Then add binary into your PATH:



Configure Kubectl
