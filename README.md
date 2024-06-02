# Kestra Flow: Coder Workspaces images

In this repository are kestra flows listed which are used to build custom Coder Workspaces container images.

### What is Kestra?
Kestra is an automation tool. You don't need Kestra to build Docker containers, but it is very comfortable
https://kestra.io/

### What is Coder Workspaces?
Coder Workspaces is a hosted development environment where you are able to use dev containers to develop.
Reference: https://coder.com/

### How to use:
To build the images you need Kestra. You can simply copy the content of one of the yaml files and place it in a blank Kestra flow. Replace the placeholders with your own values.

To run the images you have to edit the Deployment Template in your Coder Workpaces Instance. Then you are able to create a development container based on the image.

``` 
resource "kubernetes_deployment" "main" {
[...]
    template {
[...]
      spec {
[...]
        # You might need a secret name if the image repository is private
        image_pull_secrets {
          name = "SECRET_NAME"
        }

        container {
          image             = "ghcr.io/GITHUB_USERNAME/workspaces-go:0.14"
        }
      }
    }
}
``` 

In the snippet above you see the entry image_pull_secrets. This spec property depends on a pre-setup secret in your environment for loading images from a private repository. For Kubernetes you can set it up according to the Kubernetes Docs.
Reference: https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/
