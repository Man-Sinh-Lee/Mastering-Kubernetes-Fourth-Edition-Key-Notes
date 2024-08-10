### Service Account:  
- Restrict Service Account Permissions: using RBAC, least privileges.
- Namespace Isolation: Limit namespaces for SA and network policies.
- Disable Token Auto-Mounting: if pod doesn't require.
- Regularly Rotate Tokens: rotate token to mitigate leakage.
- Audit and Monitor: usage and access of SA.
- Use Separate Service Accounts for Different Workloads: avoid default, use specific SA for different workloads.

### API server is essential
- Enable and Enforce Authentication: all API requests must be authenticated, avoid anonymous and insecure methods.
- Implement Role-Based Access Control (RBAC): granular permissions for enforce least privileges
- Use Network Policies and Firewalls: limit access to API server.
- Enable Audit Logging: monitor, detect and investigate activities.
- Secure API Server Communication: Use strong TLS certificates and regularly rotate them.
- Disable Unnecessary API Endpoints: disable/remove deprecated, unused endpoints.
- Enable Admission Control Plugins: nforce security policies, validate requests, and automatically reject unsafe or misconfigured resources before they are persisted.
- Regularly Update and Patch the API Server: patch regularly to prevent vulnerabilities.
- Implement API Rate Limiting: versus DDOS attacks.
- Monitor API Server Health: performance, resource usage and logs.

### Hardening Kubernetes pods:
- Use Security Context: setup user IDs, enforce the least privileges, disable escalation. 
- Limit Capabilities: drop all capacities and add only needed ones(ex: "CHOWN", "SETUID", "SETGID").
- Enable Network Policies: control traffic flow between pods and in/out cluster.
- Set Resource Limits: limit CPUs and memory for pods.
- Read-Only File Systems: reduce risk of malicious tempering.
- Pod Security Admission: Open Policy Agent (OPA) or Kubernetes Admission Controllers.
- Secure Secrets Management: use secrets instead of environment variables.
- Isolate Containers with Namespaces: isolate teams, projects and environments.
- Enable Image Scanning: regularly scan images using Trivy/Clair.
- Deploy Minimal Base Images: use Alpine or Slim base images, regularly patches.
- Use Admission Controllers: enforce security best practices to meet industry/organization standards.
- Implement Pod Anti-Affinity Rules: pod anti-affinity rules to prevent sensitive workloads to insecure workloads.