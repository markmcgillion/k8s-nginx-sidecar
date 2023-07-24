# Nginx Sidecar Example

This repository serves as a guide to configure and use an Nginx sidecar to add security response headers in a Kubernetes environment. 🛡️

## Overview 📚

In this repository, you will find the following Kubernetes configuration files:

- `service.yaml`: This file defines a Service that exposes our application to network traffic.
- `deployment.yaml`: This file defines a Deployment that runs our application and the Nginx sidecar container.
- `configmap.yaml`: This file contains the configuration for our Nginx sidecar, specifically designed to add security response headers.

Using these files, you can deploy a secure, robust, and scalable application complete with an Nginx sidecar for added security.

## Prerequisites ☑️

Before you begin, ensure you have the following installed:

- Docker
- Kubernetes (Minikube, kubectl)
- A text editor (VS Code, Atom, etc.)

## Deployment Steps 🚀

1. **Clone the Repository** 
   
   Clone this repository to your local machine. 

   ```git clone https://github.com/yourusername/your-repo-name.git```

2. **Apply the ConfigMap**

Apply the `configmap.yaml` to create the ConfigMap resource in Kubernetes.

```kubectl apply -f configmap.yaml```

3. **Deploy the Application**

Next, deploy the application along with the Nginx sidecar using the `deployment.yaml`.

```kubectl apply -f deployment.yaml```

4. **Expose the Service**

Finally, expose the service to the outside world using the `service.yaml`.

```kubectl apply -f service.yaml```

5. **Verify the Deployment**

Check that everything is running as expected.

```kubectl get pods```

```kubectl get services```


6. **Test the Service**

Once the service is running, you can use `curl` to confirm that the headers have been added. Replace `service-url` with the URL of your service.

```curl -I service-url```

The `-I` flag tells curl to only request the headers. You should see your added headers in the response.
