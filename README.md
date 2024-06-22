<h1 align="center">
DesignSphere Wiki
</h1>

# Table of contents
1. [Design & Architecture](#h1)
    1. [TL;DR](#sh1)
    2. [Frontend](#sh2)
    4. [Backend](#sh3)
    5. [Code Generator](#sh3)



# Design & Architecture  <a name="h1"></a>
## TL;DR  <a name="sh1"></a>
* DesignSphere UI is built on Angular and uses Angular drag-and-drop CDK for the drag functionality for the UI canvas.
* Backend uses [Pulumi](https://www.pulumi.com) for deploying resources and is written in Golang. For data persistence, we use [Pebble](https://github.com/cockroachdb/pebble) KV database.
* Programmatic structures required for configuring and deploying the cloud resource are separately auto-generated from the Pulumi resource schemas
  * Example resource schema - [pulumi-aws resource schema](https://github.com/pulumi/pulumi-aws/blob/master/provider/cmd/pulumi-resource-aws/schema.json)
  * The code generator generates code for UI typescript and backend go constructs.
  * Generated code is used in rendering resource config properties in the UI and parsing the resource configs received at the backend APIs on config changes and deployment from the UI.

## Frontend  <a name="sh2"></a>
* Angular UI
* CDK drag
  
## Backend  <a name="sh3"></a>
* Golang gin-gonic web server
* Pebble data store
  
## Code Generator  <a name="sh4"></a>
* Go [Jennifer](https://pkg.go.dev/github.com/dave/jennifer) code generator 

