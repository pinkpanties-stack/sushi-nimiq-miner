# This repository is in development.

# Nimiq GPU (OpenCL & CUDA) Mining Client for AMD and Nvidia Cards
[![Github All Releases](https://img.shields.io/github/downloads/Sushipool/sushi-nimiq-miner/total.svg)]()

High-performance Nimiq GPU mining client that provides a fully open source codebase, optimized hash rate, nano protocol, multi GPU support, and a **0%** Dev fee.
## Quickstart (Ubuntu/Debian)

1. Install [Node.js](https://github.com/nodesource/distributions/blob/master/README.md#debinstall).
2. Install `git` and `build-essential`: `sudo apt-get install -y git build-essential`.
3. Install `opencl-headers`: `sudo apt-get install opencl-headers`.
4. Install OpenCL-capable drivers for your GPU ([Nvidia](https://www.nvidia.com/Download/index.aspx) or [AMD](https://www.amd.com/en/support))
5. Clone this repository: `git clone https://github.com/Sushipool/sushi-miner-opencl`.
6. Build the project: `cd sushi-miner-opencl && npm install`.
7. Copy miner.sample.conf to Parameter       Description                                            Data Type

address         Nimiq wallet address                                    [string]
                Example: "address": "Parameter       Description                                            Data Type

address         Nimiq wallet address                                    [string]
                Example: "address": "NQ...",

host            Pool server address
                Example: "host": "eu.sushipool.com"                     [string]
                
port            Pool server port
                Example: "port": "443"
                Default: 443                                            [number]

consensus       Consensus method used
                Possible values are "dumb" or "nano"
                Note that "dumb" mode (i.e. no consensus) only works with SushiPool.
                Example: "consensus": "nano"                            [string]

api             API used to control the GPU
                Possible values are "OpenCL" or "CUDA".
                NVIDIA users should use CUDA for better performance.
                Example: "api": "OpenCL"                                [string]
                
name            Device name to show in the dashboard                    [string]
                Example: "name": "My Miner"
                
hashrate        Expected hashrate in kH/s                               [number]
                Example: "hashrate": 100
                
devices         GPU devices to use
                Example: "devices": [0,1,2]
                Default: All available GPUs                              [array]
                
memory          Allocated memory in Mb for each device
                Example: "memory": [3072,3840,3840,3840]                 [array]
                
threads         Number of threads per GPU
                Example: "threads": [1,1,2,2]
                Default: 1 for OpenCL, 2 for CUDA                        [array]

cache           CUDA-only option
                Number of Argon2 blocks cached into the local GPU memory
                Example: "cache": [2,2,4,4]
                Notes: Nvidia 2080 TI = 2, Nvidia 1080 TI = 4, Nvidia 1060 = 2
                Disable: [0]
                Default: 4                                               [array]
                
memoryTradeoff  CUDA-only option
                Performs extra computations to reduce memory access
                Example: "memoryTradeoff": [192,192,192,192]
                Disable: [512] 
                Default: 192                                             [array]",

host            Pool server address
                Example: "host": "eu.sushipool.com"                     [string]
                
port            Pool server port
                Example: "port": "443"
                Default: 443                                            [number]

consensus       Consensus method used
                Possible values are "dumb" or "nano"
                Note that "dumb" mode (i.e. no consensus) only works with SushiPool.
                Example: "consensus": "nano"                            [string]

api             API used to control the GPU
                Possible values are "OpenCL" or "CUDA".
                NVIDIA users should use CUDA for better performance.
                Example: "api": "OpenCL"                                [string]
                
name            Device name to show in the dashboard                    [string]
                Example: "name": "My Miner"
                
hashrate        Expected hashrate in kH/s                               [number]
                Example: "hashrate": 100
                
devices         GPU devices to use
                Example: "devices": [0,1,2]
                Default: All available GPUs                              [array]
                
memory          Allocated memory in Mb for each device
                Example: "memory": [3072,3840,3840,3840]                 [array]
                
threads         Number of threads per GPU
                Example: "threads": [1,1,2,2]
                Default: 1 for OpenCL, 2 for CUDA                        [array]

cache           CUDA-only option
                Number of Argon2 blocks cached into the local GPU memory
                Example: "cache": [2,2,4,4]
                Notes: Nvidia 2080 TI = 2, Nvidia 1080 TI = 4, Nvidia 1060 = 2
                Disable: [0]
                Default: 4                                               [array]
                
memoryTradeoff  CUDA-only option
                Performs extra computations to reduce memory access
                Example: "memoryTradeoff": [192,192,192,192]
                Disable: [512] 
                Default: 192                                             [array]: `cp miner.sample.conf miner.conf`.
8. Edit miner.conf, specify your wallet address.
9. Run the miner `UV_THREADPOOL_SIZE=12 nodejs index.js`. Ensure UV_THREADPOOL_SIZE is higher than a number of GPU in your system.

## HiveOS Mining FlightSheet
Use the following FlightSheet settings to start mining Nimiq with HiveOS.
![HiveOS](https://github.com/Sushipool/sushi-miner-opencl/blob/master/hiveos-flightsheet.png?raw=true)

## Developer Fee
This client offers a **0%** Dev Fee!

## Nimiq GPU Support
Nvidia TITAN Xp, Titan X, GeForce GTX 1080 Ti, GTX 1080, GTX 1070 Ti, GTX 1070, GTX 1060, GTX 1050 Ti, GTX 1050, GT 1030, MX150 , Quadro P6000, Quadro P5000, Quadro P4000, Quadro P2000, Quadro P1000, Quadro P600, Quadro P400, Quadro P5000(Mobile), Quadro P4000(Mobile), Quadro P3000(Mobile)     Tesla P40, Tesla P6, Tesla P4 ,  NVIDIA TITAN RTX, GeForce RTX 2080 Ti, RTX 2080, RTX 2070, RTX 2060     Quadro RTX 8000, Quadro RTX 6000, Quadro RTX 5000, Quadro RTX 4000

## Drivers Requirements
AMD: Version 18.10 is recommended to avoid any issues.
NVIDIA: Please update to the latest Nvidia Cuda 10 drivers.

## Mining Parameters

```
Parameter       Description                                            Data Type

address         Nimiq wallet address                                    [string]
                Example: "address": "NQ...",

host            Pool server address
                Example: "host": "eu.sushipool.com"                     [string]
                
port            Pool server port
                Example: "port": "443"
                Default: 443                                            [number]

consensus       Consensus method used
                Possible values are "dumb" or "nano"
                Note that "dumb" mode (i.e. no consensus) only works with SushiPool.
                Example: "consensus": "nano"                            [string]

api             API used to control the GPU
                Possible values are "OpenCL" or "CUDA".
                NVIDIA users should use CUDA for better performance.
                Example: "api": "OpenCL"                                [string]
                
name            Device name to show in the dashboard                    [string]
                Example: "name": "My Miner"
                
hashrate        Expected hashrate in kH/s                               [number]
                Example: "hashrate": 100
                
devices         GPU devices to use
                Example: "devices": [0,1,2]
                Default: All available GPUs                              [array]
                
memory          Allocated memory in Mb for each device
                Example: "memory": [3072,3840,3840,3840]                 [array]
                
threads         Number of threads per GPU
                Example: "threads": [1,1,2,2]
                Default: 1 for OpenCL, 2 for CUDA                        [array]

cache           CUDA-only option
                Number of Argon2 blocks cached into the local GPU memory
                Example: "cache": [2,2,4,4]
                Notes: Nvidia 2080 TI = 2, Nvidia 1080 TI = 4, Nvidia 1060 = 2
                Disable: [0]
                Default: 4                                               [array]
                
memoryTradeoff  CUDA-only option
                Performs extra computations to reduce memory access
                Example: "memoryTradeoff": [192,192,192,192]
                Disable: [512] 
                Default: 192                                             [array]
```

## Recommended Settings for CUDA

```
GPU Model          GPU RAM          Memory          Cache          MemoryTradeoff          OS          Hashrate

Nvidia 1080 TI       11GB            5248             2                 256               HiveOS        458KH/S

Nvidia 1060          6GB             2816             2                 224               HiveOS        192KH/S

Nvidia 1060          3GB             1280             2                 384               HiveOS        183KH/S

Nvidia 106-100       6GB             2816             2                 384               HiveOS        160KH/S
```


### Links
Website: https://sushipool.com

Discord: https://discord.gg/JCCExJu

Telegram: https://t.me/SushiPoolHelp

Releases: https://github.com/Sushipool/sushi-miner-opencl/releases
