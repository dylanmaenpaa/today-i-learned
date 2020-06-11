# Today I learned
Documenting things I learn.

## Table of contents
- [Web](#web-development)
  * [Nginx](#nginx)
## Web development

### Nginx
Why should one use Nginx?

* **Reverse proxy**, forward requests to desired servers
* **SSL termination**, handle SSL termination outside of the application. Changing protocol from http to https inside e.g. in a node.js application is not so easy and might introduce security risks
* **gzip compression**, handle this outside of the application
* **Performance benefits**, by letting Nginx handle SSL termination and gzip compression, performance benefits can be acquired. Caching can also be done in Nginx
* **Reduce application code complexity**, instead of handling e.g. SSL termination and gzip compression inside the application code itself, we reduce the application code complexity
