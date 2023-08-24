In Kubernetes, an Ingress is an API object that manages external access to services within a cluster. It provides a way to define rules for routing traffic from external sources to the appropriate services within the cluster. An Ingress controller is a component that watches for Ingress resources and implements the rules defined in those resources by configuring the underlying load balancers, routers, or reverse proxies.

The use of an Ingress controller in Kubernetes serves several important purposes:

1. **Traffic Routing:** An Ingress controller enables you to define rules for routing incoming traffic based on criteria like hostnames, paths, or other HTTP request headers. This allows you to route traffic to different services within the cluster based on the rules you've defined.

2. **Load Balancing:** Ingress controllers often work in conjunction with external load balancers to distribute incoming traffic across multiple pods or instances of your application. This improves the availability and scalability of your services.

3. **SSL/TLS Termination:** Ingress controllers can handle SSL/TLS termination, allowing you to offload the encryption and decryption of HTTPS traffic before it reaches your application. This simplifies the management of certificates and enhances security.

4. **Name-Based Virtual Hosting:** With an Ingress controller, you can create multiple virtual hosts (domain names) that route to different services or applications within your cluster. This is useful for hosting multiple applications on the same cluster.

5. **Path-Based Routing:** You can configure Ingress rules to route traffic based on specific paths in the URL. This is useful for directing traffic to different services based on different URL paths.

6. **Fine-Grained Control:** Ingress resources provide a way to define routing and traffic rules in a declarative manner. This allows you to manage complex routing scenarios without having to configure individual load balancers or reverse proxies manually.

7. **Centralized Configuration:** Instead of configuring routing rules for each service individually, you can centralize the routing configuration using Ingress resources. This makes it easier to manage and update routing configurations.

Common Ingress controllers in the Kubernetes ecosystem include Nginx Ingress Controller, Traefik, HAProxy Ingress, and others. Each controller provides its own set of features and capabilities. You can choose the Ingress controller that best fits your requirements and integrate it with your Kubernetes cluster to enable efficient and controlled external access to your services.

https://docs.aws.amazon.com/eks/latest/userguide/aws-load-balancer-controller.html

https://docs.aws.amazon.com/eks/latest/userguide/alb-ingress.html


apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: nginx-ingress
  annotations:
    alb.ingress.kubernetes.io/scheme: internet-facing
    # alb.ingress.kubernetes.io/target-type: ip
spec:
  ingressClassName: alb
  rules:
    - http:
        paths:
          - path: /
            pathType: Prefix
            backend:
              service:
                name: nginx-service
                port:
                  number: 80
