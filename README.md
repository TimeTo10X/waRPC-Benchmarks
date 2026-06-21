<div align='center'>

### WAnime RPC Benchmarks

Benchmarks for WAnime RPC framework, against other RPC implementations

</div>

---

## Table of Contents

1. [Intro](#intro)
2. [Prerequisites](#prerequisites)
3. [WAnime RPC](#wanime-rpc)
4. [Google RPC](#google-rpc)
5. [Ice RPC](#ice-rpc)
6. [License](#license)


## Intro
These benchmarks cover three workloads:

- **nop**
- **add**
- **hex**

Each framework uses its own serialization layer:

| Framework | Serialization |
|-----------|---------------|
| waRPC     | Polyglot      |
| gRPC      | Protobuf      |
| iceRPC    | Slice         |

## Prerequisites

> [!TIP]
> If u want to avoid manual installation,
> just use `j setup` ^^ </br>
> (Works only on MacOS and Arch)

gRPC & IceRPC

- gRPC
- Protobuf
- dotnet
- cmake
- ninja
- llvm
- openssl

MacOS:
```sh
brew install grpc protobuf cmake ninja llvm openssl && brew install --cask dotnet-sdk
```
Arch btw:
```sh
sudo pacman -Syu --needed grpc protobuf dotnet-sdk cmake ninja llvm clang openssl
```

waRPC

- wapm
- wrsc
- wapm:warpc
- wapm:polyglot

Install `wapm` && `wrsc`

```sh
curl -fsSL https://wapm.wanime.io/install.sh | sh
```

```sh
curl -fsSL https://wrsc.wanime.io/install.sh | sh
```

Installing `warpc` && `polyglot`

```sh
wapm y warpc polyglot --version 0.1.0
```

## WAnime RPC

WAnime RPC (waRPC) is a modern RPC framework built on top of QUIC and written in modern c++ ^_^, by [WAnime](https://wanime.io).

**Running waRPC benchamrks:**

```sh
# Start waRPC server
j warpc_serve
```

```sh
# Run bench
j warpc_bench
```

## Google RPC

gRPC is a modern open source high performance Remote Procedure Call (RPC) framework that can run in any environment. It can efficiently connect services in and across data centers with pluggable support for load balancing, tracing, health checking and authentication. It is also applicable in last mile of distributed computing to connect devices, mobile applications and browsers to backend services.

**Running gRPC benchamrks:**

```sh
# Start gRPC server
j grpc_serve
```

```sh
# Run bench
j grpc_bench
```

## Ice RPC

A C# RPC framework built for QUIC, with bidirectional streaming, first-class async/await, and Protobuf support. 

**Running IceRPC benchamrks:**

```sh
# Start IceRPC server
j ice_serve
```

```sh
# Run bench
j ice_bench
```

## License

This project is licensed under [MIT](LICENSE) license
