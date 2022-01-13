# Transcoding gRPC to HTTP/JSON

Sample project showing how to expose a gRPC service as a HTTP/JSON api. 

There is a blogpost containing an in-depth explanation of this project

[Transcoding gRPC to HTTP JSON using Envoy](https://blog.jdriven.com/2018/11/transcoding-grpc-to-http-json-using-envoy/)

Built with Java 11, but 1.8 should also be supported, change `sourceCompatiblity` in the build.gradle to 1.8

Requirements: docker

## Getting started

1. Open the project in your favourite IDE 
     * run `./gradlew idea` or `./gradlew eclipse` to configure your IDE to detect the generated code directories.
     
1. Run `./gradlew build`   on Linux/Mac,  or `gradlew.bat build` on Windows to run a build.

1. Run `ServerMain` to start the gRPC server!

1. Run `ClientMain` to test some calls using the generated gRPC client

1. follow the steps below 

If you want to Run `./gradlew generateProto` generates sources from your .proto files  

## exposing the gRPC service as HTTP/JSON using Envoy proxy

Requirements:  
 * protoc (to generate a service definition that envoy understands)
 * docker (envoy comes in a docker container)

### Installing protoc
1. Goto: https://github.com/protocolbuffers/protobuf/releases/latest" +
2. download choose the precompiled version " +

       for linux:   protoc-3.6.1-linux-x86_64.zip" +
       for windows: protoc-3.6.1-win32.zip" +
       for mac:     protoc-3.6.1-osx-x86_64.zip" +

3. extract it somewhere in your PATH

### Installing docker

Check out this page: [Install docker](https://store.docker.com/search?offering=community&type=edition)

### Running Envoy to transcode our service

The script start-envoy.sh automates the tasks below for linux and mac:

    ./start-envoy.sh
    
