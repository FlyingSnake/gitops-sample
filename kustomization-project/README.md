# Kustomization Project

This project demonstrates the use of Kustomize to manage Kubernetes resources across different environments (development, staging, and production). 

## Project Structure

```
kustomization-project
├── base
│   ├── deployment.yaml       # Defines the Kubernetes Deployment resource.
│   ├── kustomization.yaml     # Kustomization configuration for base resources.
│   └── service.yaml          # Defines the Kubernetes Service resource.
├── overlays
│   ├── dev
│   │   ├── kustomization.yaml # Kustomization configuration for the development overlay.
│   │   └── patch-deployment.yaml # Patch for the deployment in the development environment.
│   ├── staging
│   │   ├── kustomization.yaml # Kustomization configuration for the staging overlay.
│   │   └── patch-deployment.yaml # Patch for the deployment in the staging environment.
│   └── prod
│       ├── kustomization.yaml # Kustomization configuration for the production overlay.
│       └── patch-deployment.yaml # Patch for the deployment in the production environment.
```

## Usage

1. **Install Kustomize**: Ensure you have Kustomize installed on your machine. You can find installation instructions in the [Kustomize documentation](https://kubectl.docs.kubernetes.io/).

2. **Build Base Resources**: Navigate to the `base` directory and run:
   ```
   kustomize build .
   ```

3. **Deploy to Development Environment**: Navigate to the `overlays/dev` directory and run:
   ```
   kustomize build . | kubectl apply -f -
   ```

4. **Deploy to Staging Environment**: Navigate to the `overlays/staging` directory and run:
   ```
   kustomize build . | kubectl apply -f -
   ```

5. **Deploy to Production Environment**: Navigate to the `overlays/prod` directory and run:
   ```
   kustomize build . | kubectl apply -f -
   ```

## Contributing

Feel free to submit issues or pull requests to improve this project.
