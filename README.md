

# Hyperledger Caliper Benchmarks v0.3.0
This repository contains sample benchmarks that may be used by Caliper, a blockchain performance benchmark framework. For more information on Caliper, please see the [Caliper main repository](https://github.com/hyperledger/caliper/)

This project still work in progess.

Steps to run :

1. Set your NPM project details with npm init (or just execute npm init -y) in your workspace directory (if you haven’t done this already, i.e., you don’t have a package.json file). 
```bash
npm init -y
```

2. Install the Caliper CLI  
```bash
npm install --only=prod @hyperledger/caliper-cli@0.3.1
```

3. Check the version  
```bash
npx caliper --version
```

4. Check the help file of Caliper CLI 
```bash
npx caliper --help
```

5. Bind the CLI to the required platform SDK  
```bash
npx caliper bind --caliper-bind-sut fabric:1.4.7 --caliper-bind-cwd ./
```

6.1. Copy this specified 'grpc' packages from path of 'packages' into the path of 'node_modules' 

6.2. Optional - Manually verify these group of packages mentioned below :
```
- fabric-ca-client@1.4.8
- fabric-client@1.4.7
- fabric-network@1.4.7
  -- with inside of grpc@1.24.2 (can see along with grpc_node.node)
- fabric-protos@2.0.0-snapshot.1
- grpc@1.24.2 (can see along with grpc_node.node)
```

7. Ensure the relevant chaincode (which under path of 'src') been compile using 'go build chaincode_filename.go'

8. Invoke the local CLI binary (using npx) with the appropriate parameters.
```bash
npx caliper launch master --caliper-workspace . --caliper-benchconfig benchmarks/scenario/simple/config.yaml --caliper-networkconfig networks/fabric/fabric-v1.4.1/2org2peersgoleveldb_raft/fabric-go-tls.yaml
```


### Appendix :
```
https://github.com/hyperledger/caliper-benchmarks/tree/v0.3.0

https://hyperledger.github.io/caliper/v0.3.1/getting-started/

https://wiki.hyperledger.org/display/caliper/Hyperledger+Caliper


```

