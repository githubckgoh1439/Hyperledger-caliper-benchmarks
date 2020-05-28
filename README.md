
# Hyperledger Caliper Benchmarks
This repository contains sample benchmarks that may be used by Caliper, a blockchain performance benchmark framework. For more information on Caliper, please see the [Caliper main repository](https://github.com/hyperledger/caliper/)

This project still work in progess.

Steps to run :

1. Set your NPM project details with npm init (or just execute npm init -y) in your workspace directory (if you haven’t done this already, i.e., you don’t have a package.json file). 
```bash
npm init -y
```

2. Install the Caliper CLI  
```bash
npm install --only=prod @hyperledger/caliper-cli@0.2.0
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
npx caliper bind --caliper-bind-sut fabric --caliper-bind-sdk 1.4.0
```

6. Install relevant npm packages  
```bash
npm install fabric-client@1.4.0 fabric-ca-client@1.4.0 fabric-network@1.4.0 fabric-protos@2.0.0-snapshot.1 
```

7. Copy this specified 'grpc' packages from path of 'packages' into the path of 'node_modules' 

8. Ensure the relevant chaincode (which under path of 'src') been compile using 'go build chaincode_filename.go'

9. Invoke the local CLI binary (using npx) with the appropriate parameters.
```bash
npx caliper benchmark run --caliper-workspace . --caliper-benchconfig benchmarks/scenario/simple/config.yaml --caliper-networkconfig networks/fabric/fabric-v1.4.0/2org1peergoleveldb/fabric-go.yaml
```


### Appendix :
```
https://hyperledger.github.io/caliper/v0.2/installing-caliper/

https://medium.com/@madhavi.kulkarni180796/hyperledger-caliper-benchmark-6d4d47e9d6ae
```
