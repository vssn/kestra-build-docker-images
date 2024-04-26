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
