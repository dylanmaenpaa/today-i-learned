# Today I learned
Documenting things I have learned. In this document I strive to write down knowledge in short and concise sentences.

## Table of contents
- [Unix](#unix)
  * [Comparing files](#comparing-files)
- [Web development](#web-development)
  * [Nginx](#nginx)
- [Docker](#docker)
  * [Alpine images](#alpine-images)
  * [Non-root user](#non-root-user)
- [Devops](#devops)
  * [Continous integration](#continous-integration)
  * [Continous delivery](#continous-delivery)
  * [Continous deployment](#continous-deployment)
- [Build systems](#build-systems)
  * [Cmake](#cmake)
  * [Makefiles](#makefiles)
- [Go](#go)
  * [Single standalone binary](#single-standalone-binary)
- [General](#general)
  * [Checksums](#checksums)
  
## Unix

### Comparing files
Check if files are bit-exact using **cmp**. Check if files differ line by line using diff. Use -y flag to get the files output side by side in the terminal.

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
By removing unnecessary dependencies, the images can be much smaller in size and reduce security threats. Smaller size also might give faster builds. 

### Non-root user
Run the docker daemon as non-root user to mitigate security risks. One risk is that if the user running the daemon root, malicious code might enable root access to the host machine.

## Devops

### Continous integration
When changes are pushed to the main branch, a build happens. Tests are then ran to ensure the new changes are valid.

### Continous delivery
Continous delivery brings an addition to continous integration. By automating the release process, you can easily deploy an application by clicking a button.

### Continous deployment
Continous deployment brings an addition to continous delivery. The deployment is done automatically without having to press a button as long as the prerequisites such as tests are ok.

## Build systems

### Cmake
Cmake is a build system generator, it can generate e.g. Makefiles. It is a valuable tool since make files are OS dependent, by using Cmake native Makefiles can be generated.

### Makefiles
Makefiles gives directives on how to compile and link files. It also keeps track on dependencies, thus when running Makefiles again, only neccessary build steps are made. This can greatly reduce the build time.

## Go

### Single standalone binary
A Go project usually compiles down to one single standalone binary, making it easy to deploy directly.

## General
Knowledge that doesn't need an own subtitle yet.

### Checksums
Small size data to verify if e.g. a file is not broken (which might happen during transmission or storage). A checksum function can be used, which can be like a hash function.
