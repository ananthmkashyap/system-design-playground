# Gateway API + Kubernetes Local Setup

This project demonstrates a local Kubernetes setup using **Gateway API** with **Contour** as the controller and **two backend apps** on a **KIND** cluster.  

---

## **Project Components**

1. **Cluster**: KIND (local Kubernetes cluster)
2. **Controller**: Contour (Envoy data plane)
3. **Gateway API resources**:
   - `GatewayClass`
   - `Gateway`
   - `HTTPRoute`
4. **Backend services**:
   - `backend-app-1-service` (ClusterIP, port 80)
   - `backend-app-2-service` (ClusterIP, port 80)
5. **Envoy service**:
   - LoadBalancer service installed by Contour  
   - In KIND, shows `EXTERNAL-IP: <pending>`

---

## **Current State / Issues**

### ✅ Working:
- KIND cluster is running
- Two backend apps deployed and reachable via ClusterIP
- Gateway, HTTPRoute resources exist
- Contour and Envoy pods are running
- Services can be accessed via port-forward

### ❌ Not Working / Limitations:
1. **GatewayClass not accepted / PROGRAMMED = Unknown**
   - Contour cannot attach to Gateway because GatewayClass is not correctly installed or not recognized.
   - Causes Gateway status to remain `PROGRAMMED: Unknown` and `ACCEPTED: Unknown`.
2. **Envoy LoadBalancer pending**
   - KIND does not support cloud LoadBalancers.
   - `EXTERNAL-IP` is `<pending>` (normal for local clusters).
   - Requires port-forward or NodePort to access traffic.

---

### Work in Progress
