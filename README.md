# nomadic

## what are the benefits from connecting a nomad cluster with kubernetes services (Value Add)

Integrating a HashiCorp Nomad cluster with Kubernetes services can offer several benefits in terms of managing and orchestrating workloads across both platforms. Nomad and Kubernetes serve different purposes and have different strengths, so combining them can provide a more flexible and comprehensive infrastructure. Here are some potential benefits:<br><br>

Multi-Platform Orchestration: Nomad is a flexible and lightweight orchestrator that can handle various types of workloads, including containers, VMs, and more. By connecting Nomad with Kubernetes services, you can manage a wider range of workloads across both platforms, allowing you to choose the right tool for each job.<br><br>

Unified Workload Management: By integrating Nomad and Kubernetes, you can create a unified management layer that handles tasks like deployment, scaling, and scheduling across both environments. This simplifies your operations and reduces the need for managing separate orchestration tools.<br><br>

Hybrid Cloud and On-Premises Environments: If you have a mix of on-premises infrastructure and cloud-based resources, Nomad's ability to manage both can be advantageous. You can deploy Kubernetes workloads in the cloud while using Nomad to manage workloads on your own hardware, all within the same cluster.<br><br>

Resource Optimization: Nomad has advanced features for managing resources, including support for bin packing and co-location of workloads. By connecting Nomad and Kubernetes, you can leverage Nomad's resource management capabilities to optimize resource utilization across both platforms.<br><br>

Mixed Workload Scenarios: In some cases, certain workloads might be better suited for Kubernetes, while others might work better with Nomad. By integrating them, you can choose the appropriate orchestration system for each workload, maximizing efficiency and performance.<br><br>

Ease of Migration: If you have existing applications deployed in Kubernetes and want to gradually migrate them to Nomad or vice versa, the integration can provide a smoother migration path by allowing you to manage both types of workloads within the same cluster.<br><br>

Flexibility and Choice: Nomad offers a simpler and more approachable model for orchestration compared to Kubernetes, which can be advantageous for certain use cases. By integrating the two, you provide your team with the flexibility to choose the right tool for the job without being locked into a single platform.<br><br>

Tool Diversity: By using both Nomad and Kubernetes, you avoid the risk of putting all your eggs in one basket. This diversity can be beneficial in terms of avoiding vendor lock-in and ensuring that you can adapt to changing requirements or preferences.<br><br>

### Disclaimer
It's important to note that integrating Nomad and Kubernetes might also introduce complexities related to networking, security, and management. Before embarking on such an integration, thoroughly assess your requirements, understand the trade-offs, and plan your architecture and processes accordingly.<br><br>

## Install nomad
 Dockerfiles for both RHEL 8 and Ubuntu were created using the directions located [here](https://developer.hashicorp.com/nomad/downloads). To run, in your terminal simply type: <br> 

#### Centos
>> cd Centos/RHEL8 <br>
>> docker build . -t rhel-nomad <br>
>> docker run -it rhel-nomad <br>

#### Ubuntu
>> cd Ubuntu/Nomad
>> docker build . -t ubuntu-nomad <br>
>> docker run -it ubuntu-nomad <br>

If the build is succesful, nomad will be installed and if you type:<br>
>> nomad -v <br> 

in your terminal the next 3 lines should be something similar to: <br> 
>> Nomad v1.6.1<br>
>> BuildDate 2023-07-21T13:49:42Z<br>
>> Revision 515895c7690cdc72278018dc5dc58aca41204ccc <br>