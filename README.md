## `graph`

Prototype interactive SVG frontend UI for the `graph` API system

![draw-ui](topology1.svg)

UI demo at: http://draw.apnex.io  

### What is it
`graph` is aKubernetes application that dynamically provisions micro-router PODs into the current namespace
These `nodes` are constructed via a drag-and-drop style drawing UI along with network connections between them.

`graph` also:
-- Is lightweight
-- Creates and destroys `nodes` on demand within a namespace
-- Responsive - leverages websockets for dynamic client/server state

This application has no inherent utility, and is considered a toy as a demo workload within a cluster.

---
### Install
`graph` requires any functioning Kubernetes cluster to deploy to.
**Note:** Please ensure your cluster is configured to support Service Type=Loadbalancer for UI access

```
kubectl apply -f apnex.io/graph/deploy.yaml
```

This will deploy the `graph-server` pod into the current namespace (i.e default).  
It will also configure a Service Type=Loadbalancer for access.  
If you wish to use another namespace, change the kubectl context or add the `--namespace` flag to commands.  

View the external IP as follows:
```
kubectl get 
```

---
### Interface Usage
#### Nodes
- Click and hold `right-click` on the dock and drag mouse to `create` new `node` onto page
- Click and hold `right-click` on an existing `node` and drag mouse to move it
- Hold `ALT + right-click` on a `node` to `delete` it, along with all connected `links`
- Hold `CTRL + right-click` on a `node` to `copy` it, then drag mouse to new location

#### Links
- Hold `left-click` on a `node` and drag mouse to create a new `link` between 2 nodes
- Hold `left-click` on a `node` and drag mouse to create a new `link` between 2 nodes

#### Zones
- Hold `SHIFT` to view `zone` grid
- Hold `SHIFT` and drag `left-click` to create a new `zone`
- Hold `SHIFT + ALT` and `right-click` to delete an existing zone
