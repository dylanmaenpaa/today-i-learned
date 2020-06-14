# Today I learned
Documenting things I have learned. In this document I strive to write down knowledge in short and concise sentences.

## Table of contents
- [Web development](#web-development)
  * [Nginx](#nginx)
- [Docker](#docker)
  * [Alpine images](#alpine-images)
  * [Non-root user](#non-root-user)
- [Devops](#devops)
  * [Continous integration](#continous-integration)
  * [Continous delivery](#continous-delivery)
  * [Continous deployment](#continous-deployment)
## Web development

### Nginx
Why should one use Nginx?

* **Reverse proxy**, forward requests to desired servers.
* **SSL termination**, handle SSL termination outside of the application. Changing protocol from http to https inside e.g. a node.js application is not so easy and might introduce security flaws.
* **gzip compression**, handle this outside of the application.
* **Performance benefits**, by letting Nginx handle SSL termination and gzip compression, performance benefits can be acquired. Caching can also be done in Nginx.
* **Reduce application code complexity**, instead of handling e.g. SSL termination and gzip compression inside the application code itself, we reduce the application code complexity.

## Docker

### Alpine images
By removing unnecessary dependencies, the images can be much smaller in size. Smaller size gives faster builds.

### Non-root user
Run the docker daemon as non-root user to mitigate potential vulnerable security risks. One risk is that if the user running the daemon root, malicious code might enable root access to the host machine.

## Devops

### Continous integration
When changes are pushed to the main branch, a build happens. Tests are then ran to ensure the new changes are valid.

### Continous delivery
Continous delivery brings an addition to continous integration. By automating the release process, you can easily deploy an application by clicking a button.

### Continous deployment
Continous deployment brings an addition to continous delivery. The deployment is done automatically without having to press a button as long as the prerequisites such as tests are ok.
