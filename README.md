# C++ project to set up bamboo and sonar

## Objective: test test test

## In your Bamboo plan, add tasks:
- Script Task - Compile C++ APP with Build Wrapper

### Build the C++ project using Build Wrapper
```shell
#!/bin/bash

# Move into your C++ app directory
cd /home/bamboo-agen/cpp-app

# Clean any previous build-wrapper output
rm -rf bw-output

# Run Cmake and Build using the BUild Wrapper
/opt/build-wrapper/
build-wrapper-linux-x86-64 \
    --out-dir bw-output \
    bash -c "cmake . && make"
```

### Run SonarScanner
```shell
#!/bin/bash

cd /home/bamboo-agent/cpp-app

/opt/sonar-scanner/bin/sonar-scanner
```