# WireMock Studio Kubernetes Example

WireMock Studio can be deployed into a Kubernetes cluster using the manifest in this project.

To get started, ensure you have `kubectl` installed, are authenticated against the Kubernetes cluster you
wish to deploy into.

Run the following command in a terminal to initiate the deployment:

```bash
kubectl apply -f wiremock-studio.yaml --namespace <target namespace>
```

This will create the following resources:

* A `ServiceAccount` for WireMock Studio to use for cluster operations.
* A `Role`, allowing read/write access to all Services in the namespace.
* A `RoleBinding`, associating the role with the default service account in the namespace.
* A `PersistentVolumeClaim` for stub and config storage.
* A `Deployment` for the WireMock Studio app.
* A `Service` of type `LoadBalancer` (externally accessible) for the app.

