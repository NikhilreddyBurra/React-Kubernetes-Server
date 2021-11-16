# Using the Scripts
> We can use these Scripts to deploy the React App in the company's own server.

### Steps to Deploy
---
1. Create an appropriate Dockerfile for the application
2. Build the docker image: 

   ```sh
   docker build -t <url-of-user>/<name-of-repo>:<tag>
   ```
3. Run the Docker image and test it locally
 
   ```sh
   docker run -d -p 3000:3000 <url-of-user>/<name-of-repo>:<tag>
   ```
4. Now, if the image is running properly locally, you are ready to deploy the app on Kubernetes Server
5. Use `deploy.yaml` file to deploy the pods and services. 

   ```sh
   # Check if pod is running
   kubectl get po
   
   # Check if service is running
   kubectl get svc
   ```
6. Use `nginx-ingress.yaml` file to create an Nginx Ingress Controller to redirect the Application's Cluster IP to Digital Ocean.

   ```sh
   # Check if IP is alloted to the service we deployed
   kubectl get ing
   ```
7. Here, you will get the public IP, map that IP to DNS mapping.
