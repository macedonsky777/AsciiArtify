
# Local Kubernetes Development Comparison

This repository compares different tools for setting up local Kubernetes clusters: k3d, Minikube, and kind.

| Skills                          | k3d Features/Technologies                                    | Minikube Features/Technologies                           | kind Features/Technologies                                |
|---------------------------------|--------------------------------------------------------------|----------------------------------------------------------|----------------------------------------------------------|
| **Setup and Installation**      | - Quick and easy setup using Docker containers               | - Single-node Kubernetes cluster on local machine        | - Runs Kubernetes clusters using Docker container nodes  |
| **Resource Requirements**       | - Lightweight, minimal resource usage                        | - Can be resource-intensive depending on configuration   | - Moderate resource usage, requires Docker                |
| **Supported Environments**      | - Linux, macOS, Windows                                      | - Linux, macOS, Windows                                  | - Linux, macOS, Windows                                  |
| **Cluster Configuration**       | - Multi-node cluster support                                 | - Supports multi-node clusters with profiles             | - Multi-node cluster support                             |
| **Storage Options**             | - Uses host storage                                          | - Supports multiple storage provisioners                 | - Uses Docker volumes for storage                        |
| **Networking**                  | - Uses Docker network                                        | - Supports various network plugins                       | - Uses Docker network                                    |
| **Extensions and Add-ons**      | - Supports k3s add-ons                                       | - Supports Minikube addons                               | - Supports kind-specific add-ons                         |
| **Performance**                 | - Fast startup and shutdown                                  | - May have slower startup compared to k3d and kind       | - Fast startup and shutdown                              |
| **Integration**                 | - Well-integrated with Docker ecosystem                      | - Supports various container runtimes                    | - Well-integrated with Docker ecosystem                  |
| **Use Cases**                   | - Ideal for CI/CD pipelines, local development               | - Local development, testing complex configurations      | - Ideal for testing Kubernetes clusters, CI/CD           |
| **Kubernetes Version Support**  | - Supports latest k3s releases                               | - Supports a wide range of Kubernetes versions           | - Supports the latest Kubernetes releases                |
| **Community and Support**       | - Growing community, good support from Rancher               | - Large community, extensive documentation               | - Growing community, good support from Kubernetes SIGs   |
| **Pros for Startups**           | - Very fast and lightweight; perfect for quick iterations    | - Rich feature set; supports various add-ons             | - Simple setup; excellent for CI environments            |
| **Cons for Startups**           | - Limited to k3s; fewer features compared to full Kubernetes | - Can be slow to start and resource-intensive            | - Requires Docker; fewer features compared to Minikube   |

## Demo

Here is a demonstration of setting up a local Kubernetes cluster using k3d:

![Demo of k3d setup](assets/k3d.gif)

## Demo

Here is a demonstration of setting up a local Kubernetes cluster using kind:

![Demo of k3d setup](assets/kind.gif)

## Demo

Here is a demonstration of setting up a local Kubernetes cluster using minikube:

![Demo of k3d setup](assets/minikube.gif)


Conclusion: As for me, kind and k3d feels more lightwaight and more modern. Low resource usage, good and simple documentation.
All tools are well documented and have experemental features of Podman support, minikube closest to oroginal k8s architecture and oldest, so have more resolved cases and modules, what can help simulate testing on final stages. But, even if we look on some problems with docker licencing, conclusion need to be based on goals. For serious project additional support from Docker and its gold standartization can be best chose for future perspective. So, due to that, I reccomend choose kind for local development and think it's enough for most cases.
