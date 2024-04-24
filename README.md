# Kubernetes-workshop
Spin up a basic deployment and service serving a basic hello world node app
<br/>
<br/>
<br/>

## Getting started with Kubernetes
1. Download and install Docker for desktop: https://www.docker.com/products/docker-desktop/
2. Under the dashboard settings for Docker for desktop, select Kubernetes and check the enable Kubernetes box
3. From the Kubernetes section of the application drop down, ensure `docker-desktop` is selected

## Installing kubectl
If on MacOS:
1. `brew install kubectl`

Or install from binary:
1. Download the release based on your OS and Arch here: https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/
2. Make the binary executable with: `chmod +x ./kubectl`
3. Move the binary to a location on your system PATH
   ```
   sudo mv ./kubectl /usr/local/bin/kubectl
   sudo chown root: /usr/local/bin/kubectl
   ```
Verify the cli is installed by running `kubectl get pods -A` 

<br/>

## Starting the workshop
Basic configs are provided in the starter folder if you want a jumping off point. Or if you prefer you can try making the manifests from scratch!
There is a provided Dockerfile built and pushed to Dockerhub you can use which just logs and echoes back the path you send to the server. The image is `mitchhamm/kubernetes-workshop:1.0.0`

## Outcomes
Upon creating the resources correctly, visiting `localhost:<service-port>` should give you a hello world prompt followed by the path you specified. 

## Next Steps
If you've got the application running locally on kubernetes successfully, try increasing the replica count on the deployment to spin up more pods. From here you can grab logs from each of the pods to see that the requests are actually being routed to different pods each time to spread the load across the pods
