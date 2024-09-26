# Void: Cloud-Native Node Hibernation Framework

Void is a cloud-native framework designed to hibernate and manage bare-metal worker nodes in Kubernetes clusters. It enables efficient resource utilization, cost savings, and environmental sustainability by automatically identifying and hibernating underutilized nodes while ensuring seamless application continuity.

> [!Warning]
> Void project is still in an early stage which means that any feature changes are very welcome and the features aren't 100% feasible.

## Key Features
- **Automated Hibernation:** Void monitors node utilization and triggers hibernation for idle nodes based on user-defined policies.
- **Seamless Wake-up:** Nodes wake up based on workload demand, ensuring minimal disruption.
- **Resource Optimization:** Dynamic node state adjustments optimize resource allocation.
- **Kubernetes Integration:** Fully integrates with Kubernetes APIs for centralized management.
- **Scalable and Reliable:** Designed for scalability and reliability in production environments.

## Initial Workflow (Further research needed)

1) **Monitoring Node Utilization:** Continuously monitor CPU, memory, and custom metrics to determine node activity.
2) **Define Hibernation Policies:** Create policies specifying conditions for hibernating nodes based on resource thresholds.
3) **Trigger Hibernation:** Execute commands or API calls to put nodes into low-power states (e.g., using server power management features or out-of-band tools like IPMI).
4) **Preserve Data and State:** Gracefully shut down applications, move services to other nodes, and preserve data/configurations.
5) **Manage Wake-up Criteria:** Monitor workload demand and define criteria for waking up hibernated nodes based on increased demand or specific service needs.
6) **Integrate with Kubernetes:** Use Kubernetes APIs to update node states, coordinate with the scheduler, and manage resource distribution.
7) **Monitor Health:** Continuously check hibernated node health, perform periodic checks, and take corrective actions if issues arise.
   
## Challenges

> [!Important]
> The challenge with running and managing bare metal K8s clusters today is that servers and operating systems are managed separately from the K8s nodes lifecycle.

**Resource Fluctuations:**
Handle rapid changes in resource utilization to avoid early hibernation.

**Workload Variability:**
Manage varying workloads to prevent unnecessary node state changes.

**Critical Services:**
Prioritize critical services to prevent hibernation disruptions.

**Scheduled Jobs:**
Adjust hibernation criteria for periodic workload changes.

**High Availability:**
Implement failover mechanisms to maintain service continuity.

**Graceful Shutdown:**
Ensure applications gracefully shut down before hibernation.

**Health Checks:**
Perform health checks to verify node and application readiness.

**Pending Tasks:**
Handle pending tasks or operations before hibernation.

**Emergency Wake-up:**
Implement rapid response procedures for critical situations.

**Fault Tolerance:**
Handle failures and provide error recovery mechanisms.

## Development Tech Stack

### Primary programming language for development

- Go Language:
  
Go Language Docs: https://go.dev/

- Rust/C (Optional):
Utilized for interacting with the operating system and triggering hibernation.

### Prometheus Integration

- Prometheus Client Library:
Instrument metrics for monitoring.

Prometheus Client Library Docs: https://prometheus.io/docs/instrumenting/clientlibs/

- Prometheus Node Exporter:
Collect system metrics for monitoring.

Prometheus Node Exporter Docs: https://prometheus.io/docs/guides/node-exporter/

### Kubernetes Tools

- Operator SDK:
Build Kubernetes operators for automation.

Operator SDK Docs: https://sdk.operatorframework.io/

- Kubebuilder:
SDK for building Kubernetes APIs using CRDs.

Kubebuilder Docs: https://book.kubebuilder.io/

- ClusterAPI
Cluster API is a project that brings K8s-style APIs and an “end-state” approach to cluster lifecycle management (creation, configuration, upgrade, destruction).

ClusterAPI Docs: https://cluster-api.sigs.k8s.io/

## Additional resources

Article for creating your first CRD: https://refactorfirst.com/create-kubernetes-custom-resource-definition-crd

Metal as a service from canonical: https://maas.io/

Great Bare Metal tools: https://github.com/alexellis/awesome-baremetal

Very useful blog about provisioning bare metal k8s with cluster API: https://thenewstack.io/provision-bare-metal-kubernetes-with-the-cluster-api/

Cloud to a datacenter: https://metal-stack.io/

Found while researching hibernation triggering: 

- https://www.kernel.org/doc/html/v5.8/power/basic-pm-debugging.html
- https://docs.kernel.org/admin-guide/pm/sleep-states.html

## Getting Started
...

## Contribution 
...

## License
Void is licensed under the [Apache License 2.0](https://github.com/Void-k8s/Void/blob/main/LICENSE)
