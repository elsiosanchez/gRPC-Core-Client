# ADempiere Core Client for gRPC

[![npm version](https://img.shields.io/npm/v/@adempiere/grpc-core-client.svg)](https://www.npmjs.com/package/@adempiere/grpc-core-client)
[![License](https://img.shields.io/npm/l/@adempiere/grpc-core-client.svg)](https://github.com/erpcya/adempiere-gRPC-Server/blob/master/LICENSE)
[![Downloads](https://img.shields.io/npm/dm/@adempiere/grpc-core-client.svg)](https://www.npmjs.com/package/@adempiere/grpc-core-client)

ADempiere Core Client write in Javascript for gRPC service, use it for connect with
[ADempiere-gRPC-Server](https://github.com/erpcya/adempiere-gRPC-Server).

## Requirements
- [Envoy Proxy](https://www.envoyproxy.io/)
- [Envoy Pre-configured Proxy](https://github.com/erpcya/gRPC-Envoy-Proxy)

## Using it

``` bash
# installing via NPM
npm install @adempiere/grpc-core-client
```
``` bash
# installing via Yarn
yarn add @adempiere/grpc-core-client
```

## Recreate proto stub class (only for contribute to project)
For recreate stub class you must have follow:
- [protobuf](https://github.com/protocolbuffers/protobuf/releases)
- [protoc](https://github.com/grpc/grpc-web/releases)
- Also you can see it: [gRPC-web](https://github.com/grpc/grpc-web)
- [gRPC](https://grpc.io/docs/tutorials/basic/web.html)

After installed it just go to source code folder an run it:

Base Data Type
```
protoc proto/base_data_type.proto \
--js_out=import_style=commonjs:src/grpc \
--grpc-web_out=import_style=commonjs,mode=grpcwebtext:src/grpc
```

Core Functionality
```
protoc proto/core_functionality.proto \
--js_out=import_style=commonjs:src/grpc \
--grpc-web_out=import_style=commonjs,mode=grpcwebtext:src/grpc
```

The result is generated on: src/grpc folder
- `base_data_type_pb.js`
- `core_functionality_grpc_web_pb.js`
- `core_functionality_pb.js`