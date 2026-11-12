# Kubernetes Study Guide

This repository serves as a comprehensive study guide and practical reference for learning Kubernetes. It contains hands-on examples, configurations, and notes organized by topic to support your Kubernetes learning journey.

## 📚 Course Reference

This repository is based on the course: **[Kubernetes with HELM: Kubernetes for Absolute Beginners](https://www.udemy.com/course/kubernetes-training/?srsltid=AYCX9vL-S-u3goVljhUxl_vQTmqa6s5lNEGB27NKSsgmoZpkKePL1K5C)**

Available on Udemy, this course provides a solid foundation for understanding Kubernetes concepts from scratch.

## 📁 Repository Structure

```
k8s_guide/
├── introduction_k8s/          # Basic Kubernetes deployments
│   ├── mysql-deployment.yaml
│   └── wordpress-deployment.yaml
├── pods_and_containers/       # Pod and container configurations
│   ├── nginx-pod.yml
│   ├── nginx-service.yml
│   ├── configmap-env-demo.yml
│   ├── configmap-posix-demo.yml
│   ├── configmap-vol-demo.yml
│   ├── example-configmap.yml
│   ├── example-posix-configMap.yml
│   ├── example-secret.yml
│   ├── nginx.conf
│   └── .htpasswd
├── k8sObjectManagement/       # RBAC and object management
│   ├── pod.yml
│   ├── pod-reader-role.yaml
│   ├── pod-reader-rolebinding.yml
│   ├── pod-reader-service-account.yml
│   └── service-account-binding.yml
├── cluster-kind/              # Kind cluster configurations
│   ├── config
│   └── config.yaml
└── wordpress/                 # WordPress application examples
```

## 🚀 Getting Started

### Prerequisites

- Kubernetes cluster (local or cloud)
- kubectl CLI tool installed
- Docker installed (for container images)
- (Optional) Kind for local Kubernetes clusters

### Setting up a Local Cluster with Kind

If you want to practice locally using Kind:

```bash
# Install Kind (if not already installed)
# For Linux:
go install sigs.k8s.io/kind@latest

# Create a cluster using the provided configuration
kind create cluster --config cluster-kind/config.yaml

# Verify the cluster is running
kubectl cluster-info
kubectl get nodes
```

### Applying Configurations

Navigate to any directory and apply the YAML files:

```bash
# Example: Apply WordPress deployment
kubectl apply -f introduction_k8s/wordpress-deployment.yaml

# Example: Apply a pod configuration
kubectl apply -f pods_and_containers/nginx-pod.yml

# Example: Apply RBAC configurations
kubectl apply -f k8sObjectManagement/
```

## 📖 Study Topics

### 1. Introduction to Kubernetes

- Basic concepts and architecture
- Deploying applications (MySQL and WordPress examples)
- Understanding deployments and services

### 2. Pods and Containers

- Creating and managing pods
- Container configuration
- Multi-container pods

### 3. Configuration Management

- **ConfigMaps**:
  - Environment variable injection
  - POSIX-style configuration
  - Volume-based configuration
- **Secrets**:
  - Managing sensitive data
  - Base64 encoding/decoding

### 4. Kubernetes Object Management

- Role-Based Access Control (RBAC)
- Service Accounts
- Roles and RoleBindings
- Security contexts

### 5. Local Development

- Kind cluster setup
- Local cluster configuration
- Testing configurations locally

## 🛠️ Common Commands

```bash
# Get all pods
kubectl get pods

# Get all services
kubectl get services

# Describe a pod
kubectl describe pod <pod-name>

# View pod logs
kubectl logs <pod-name>

# Delete a resource
kubectl delete -f <filename.yaml>

# Apply configuration
kubectl apply -f <filename.yaml>

# Get configmaps
kubectl get configmaps

# Get secrets
kubectl get secrets

# Describe a service account
kubectl describe serviceaccount <sa-name>
```

## 📝 Adding Your Notes

This repository is designed to grow with your learning. To add your own notes:

1. Create a new directory for your topic
2. Add YAML configurations and markdown documentation
3. Update this README with the new structure
4. Commit your changes with descriptive messages

Example:

```bash
mkdir -p my_new_topic
echo "# My Study Notes" > my_new_topic/notes.md
git add .
git commit -m "Add study notes for new topic"
```

## 🔗 Useful Resources

- [Kubernetes Official Documentation](https://kubernetes.io/docs/)
- [kubectl Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [Kind Documentation](https://kind.sigs.k8s.io/)
- [Udemy Course: Kubernetes with HELM](https://www.udemy.com/course/kubernetes-training/)

## 📄 License

This project is licensed under the terms specified in the [LICENSE](LICENSE) file.

## 🤝 Contributing

This is a personal study guide, but feel free to fork and adapt it for your own learning journey.

---

**Happy Learning! 🎓**
