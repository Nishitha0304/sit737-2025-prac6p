Step-by-Step Instructions:
1. Install Docker Desktop, Node.js, and enable Kubernetes in Docker Desktop settings.
2. Create a new folder and initialize a Node.js project using npm init -y.
3. Install Express using: npm install express.
4. Create app.js to serve a basic message “Hello from Docker container!” on port 3000.
5. Create package.json with the default configuration and Express as a dependency.
6. Create a Dockerfile that sets up a Node.js base image, copies app files, installs dependencies, exposes port 3000, and runs the app.
7. Build Docker image using:
docker build -t node-kube-app .
8. Tag the image for Docker Hub:
docker tag node-kube-app nishitha03/node-kube-app
9. Push the image to Docker Hub:
docker push nishitha03/node-kube-app
10. Create a deployment.yaml to deploy the app on Kubernetes with 2 replicas using the Docker Hub image.
11. Apply the deployment:
kubectl apply -f deployment.yaml
12. Create a service.yaml file to expose the app using a NodePort (30036).
13. Apply the service:
kubectl apply -f service.yaml
14. Open your browser at http://localhost:30036 to verify that the app is running.
15. Run kubectl get pods and kubectl get svc to confirm that the app is deployed and exposed successfully.
