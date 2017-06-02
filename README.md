# kubernetes-101

The following code can used to deploy a python app which has redis as backend. These service can be executed using Docker nad Kubernetes. PFB the steps for the same.

1. Docker (Go to Docker folder)

Step 1: Run the build.sh file to create the required image. 
CMD: ./build.sh

Step 2: Verify the above step by checking the docker images using 'docker images' command. Now tag the imnage created above using the below command: 

CMD: docker tag <your image_id> <Docker-repo>/webapp-demo

Step 3: Now push the image to your docker repo.

Step 4: Now change the Docker repo name in the docker-compose.yml file and run the following command:

docker-compose up


2. Kubernetes (Go to Kubernetes folder)

Step 1: Run the following commands on the kubernetes master:

kubectl create -f db-pod.yml

kubectl create -f db-svc.yml

Confirm the same using the command : "kubectl get pods"  "kubectl get svc"

Step 2: Run the following commands on the kubernetes master:

kubectl create -f web-pod.yml

kubectl create -f web-svc.yml

Confirm the same using the command : "kubectl get pods"  "kubectl get svc"

Step 3: Now confirm the same by hitting any node IP at the nodeport which you get in the output of following command: "kubectl describe svc web"

