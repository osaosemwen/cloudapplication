## Install Minikube 

This enable you to easily deploy and test your kubernetes clusters housing your applications on your local machine before pushing it to the cloud. It should be noted that Minikube only enables you to run a single node Kubernetes cluster in a VM, givinig the ability to test and develop your Applications. it should be noted that Minikube supports kubernetes features such as: Dashboards, DNS, ConfigMAps, Container Runtime etc. (Which I would show, if needed....) Since Minikube is still in its development stage, I would refer you to this link to download the version you want for your system (https://github.com/kubernetes/minikube/blob/v0.23.0/CHANGELOG.md). In my case I am using Linux hence this is the command I use to install minicube: curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.23.0/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/ If you are using OSX: use this link: curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.23.0/minikube-darwin-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin Confirm installation ( $ minikube version : ↵ minikube version: v0.23.0) Confirm IP: (in most situation it returns the local ip of the system) : ( $ minikube IP : ↵ 192.168.1.100)

Quick Start: ``` $ minikube start ........↵``` 

Starting local Kubernetes v1.8.0 cluster... Starting VM... Getting VM IP address... Moving files into cluster... Setting up certs... Connecting to cluster... Setting up kubeconfig... Starting cluster components... Kubectl is now configured to use the cluster.

Now just as you can deploy a simple container image for applications on docker machine (.....) you can do the same for minikube, In this case running cluster of kubernetes for applications.

Simple Start: (Run-Hello World minikube image) use this link: ( $ kubectl run hello-minikube --image=gcr.io/google_containers/echoserver:1.4 –port=8080 ↵ deployment "hello-minikube" created) Now the cluster is configured in minikube: with container housing echoserver on port 8080, the next is to expose the port, for it to be assesible on your local machine browser: ( $ kubectl expose deployment hello-minikube –type=NodePort ↵service "hello-minikube" exposed Now similar to how you see if an application in a conatiner image is up and running on Dockers, In minikube, this will show all containers and clusters created in minkube type this on minikube ($ kubectl get pod: NAME READY STATUS RESTARTS AGE frontend-685922934-7ydhf 1/1 Running 2 3h frontend-685defefe- 9frgr 1/1 Running 2 3h frontend-685d7ff496-rnnpv 1/1 Running 2 3h hello-minikube-5bc754d4cd-qsqlq 1/1 Running 0 9m

Note: if the staus is ContainerCreating, be patient enter the command again, until the status changes to ContainerCreated. Then you can curl the application on terminal ($ curl $(minikube service hello-minikube –url CLIENT VALUES: client_address=172.17.0.1 command=GET real path=/ query=nil request_version=1.1 request_uri=http://192.168.1.100:8080/

SERVER VALUES: server_version=nginx: 1.10.0 - lua: 103471

HEADERS RECEIVED: accept=/ host=192.168.1.100:3182 user-agent=curl/7.85.1 BODY: -no body in request) since no http server is deployed we leave that to future projects: To delete the hello-project: $ kubectl delete deployment hello-minikube ↵ deployment "hello-minikube" deleted if you want to see a GUI of your minikube $ minikube dashboard this will show you a open in your browser a page where you can view and manage your pods.

Hence I have been able to show how to create your cluster Up and running deploy a simple application on it and delete the application on it.

Projects on MiniKube: Project 1: kubectl get pod: NAME READY STATUS RESTARTS AGE
frontend-685922934-7ydhf 1/1 Running 2 3h
frontend-685defefe- 9frgr 1/1 Running 2 3h
frontend-685d7ff496-rnnpv 1/1 Running 2 3h
hello-minikube-5bc754d4cd-qsqlq 1/1 Running 0 9m

Note: if the staus is ContainerCreating, be patient enter the command again, until the status changes to ContainerCreated. Then you can curl the application on terminal ($ curl $(minikube service hello-minikube –url CLIENT VALUES:
client_address=172.17.0.1
command=GET
real path=/
query=nil
request_version=1.1
request_uri=http://192.168.1.100:8080/

SERVER VALUES:
server_version=nginx: 1.10.0 - lua: 103471

HEADERS RECEIVED:
accept=/
host=192.168.1.100:3182
user-agent=curl/7.85.1
BODY:
-no body in request) since no http server is deployed we leave that to future projects:
To delete the hello-project: $ kubectl delete deployment hello-minikube ↵ deployment "hello-minikube" deleted
if you want to see a GUI of your minikube
$ minikube dashboard this will show you a open in your browser a page where you can view and manage your pods.

Hence I have been able to show how to create your cluster Up and running deploy a simple application on it and delete the application on it.

Projects on MiniKube:
Project 1:





