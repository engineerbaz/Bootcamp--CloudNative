# Service

Service is Virtual LoadBalancer intended to allow reachablity between resources
1. ClusterIP
2. NodePort
3. LoadBalancer

Type 1 and 2 are available in on-premises only

## NodePort

It has 3 ports only one is Madontory to mention

- NodePort (port of host between 30000 -- 32767)
- Port (port of service and pod)
- TargetPort (Madontory field, Port of the target like Pod)

     **NodePort --> Port --> TargetPort**

  --------   ----   -----------
| NodePort | Port | TargetPort  |
| : ---    | :--- | :--- |



  --------   ----   -----------

## ClusterIP

