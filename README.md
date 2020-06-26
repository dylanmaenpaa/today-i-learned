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
- [C/C++](#c-c--)
  * [Portability between platforms](#portability-between-platforms)
- [Go](#go)
  * [Single standalone binary](#single-standalone-binary)
- [General](#general)
  * [Checksums](#checksums)
- [Software licenses](#software-licenses)
  * [General Public License (GPL)](#general-public-license--gpl-)
  * [Lesser General Public License (LGPL)](#lesser-general-public-license--lgpl-)
  * [MIT license](#mit-license)
  
## Unix

### Comparing files
Check if files are bit-exact using **cmp**. Check if files differ line by line using **diff**. For diff use the -y flag to get the lines output side by side in the terminal.

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
When changes are pushed to the main branch, a build happens. Tests are then ran to ensure that the new changes are valid.

### Continous delivery
Continous delivery brings an addition to continous integration. By automating the release process, you can easily deploy an application by clicking a button.

### Continous deployment
Continous deployment brings an addition to continous delivery. The deployment is done automatically without having to press a button as long as the prerequisites such as tests are ok.

## Build systems

### Cmake
Cmake is a build system generator, it can generate e.g. Makefiles. It is a valuable tool since make files are OS dependent, by using Cmake native Makefiles can be generated.

### Makefiles
Makefiles gives directives on how to compile and link files. It also keeps track on dependencies, thus when running Makefiles again, only neccessary build steps are made. This can greatly reduce the build time.

## C/C++

### Portability between platforms
Use datatypes such as `int32_t` from stdint.h/cstdint.h to ensure that the code is platform independent. This makes the datatypes have the same size. E.g. the size of `unsigned long` might be 8 bytes in a 64-bit system, whereas `unsigned long` in a 32-bit system might only be 4 bytes. Using `int32_t` ensures that the size is 4 bytes on both platforms.

## Go

### Single standalone binary
A Go project usually compiles down to one single standalone binary, making it easy to deploy directly.

## General
Knowledge that doesn't need an own subtitle yet.

### Checksums
Small size data to verify if e.g. a file is not broken (which might happen during transmission or storage). A checksum function can be used, which can be like a hash function.

## Software licenses

### General Public License (GPL)
If the GPL software is improved and released to the public, the altered source code must also be publically available under the GPL license. Organisations, companies or privately can use GPL software internally without ever releasing it to the public.

### Lesser General Public License (LGPL)
Developers and companies does not need to share their own source code when using non-modified LGPL software in their own software. However if the LGPL software is modified and publically distributed, the modified version needs to be under LGPL license aswell.

### MIT license
The MIT license is very permissive. Basically everything is allowed as long as you include the MIT copyright notice.
