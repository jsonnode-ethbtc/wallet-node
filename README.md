# WalletConnect NodeServer ⏮️🖥️⏭️

Node Server for relaying WalletConnect connections

## Development 🧪

Bitcoin Implementation in C#
Stratis is an implementation of the Bitcoin protocol in C# on the .NET Core platform.
The node can run on the Bitcoin and Stratis networks.
Stratis Bitcoin is based on the NBitcoin project.

For Proof of Stake support on the Stratis token the node is using NStratis which is a POS implementation of NBitcoin.

.NET Core is an open source cross platform framework and enables the development of applications and services on Windows, macOS and Linux.

Compiler requirements
Compilier	Minimum Version
gcc/g++	5.0
clang++	3.4 (8.0.0)
C++ compiler support C++14. Using c++ -v to check c++ version.

Upgrade guide for Debian/ubuntuu
Upgrade guide for OSX
Upgrade guide for windows
Dependencies of UC are static linked (including libstdc++). Thus, there is no extra dependency after compilation. Recommends Ubuntu 16.04/CentOS 7.2/MinGW to develop/debug/build UC.

Toolchain requirements
cmake 3.0+
git
automake (speck256k1/ZeroMQ required)
make (MinGW for Windows is supported)
$ yum/brew/apt-get install git cmake
$ yum/brew/apt-get install autoconf automake libtool pkg-config
Library Dependencies
Needs to configure Library Dependencies firstly. Installing by bash script (sudo required).

$ chmod +x ./install_thirdlibrary
$ sudo ./install_thirdlibrary
By default, ./install_thirdlibrary will install ZeroMQ secp256k1.
You can install more by specify arguments, for example:

# --build-upnpc is needed is you want UPnP supporting.
$ sudo ./install_thirdlibrary --build-boost --build-upnpc
boost 1.60(boost is required and 1.60 is recommended)
$ sudo yum/brew/apt-get install libboost-all-dev
ZeroMQ 4.2.5+(required)
Modules server/explorer required.

$ wget https://github.com/zeromq/libzmq/releases/download/v4.2.5/zeromq-4.2.5.tar.gz
$ tar -xzvf zeromq-4.2.5.tar.gz
$ cd zeromq-4.2.5
$ ./autogen.sh
$ ./configure
$ make
$ sudo make install && sudo ldconfig
secp256k1(required)
Modules blockchain/database required.

$ git clone https://github.com/UCHAIN-WORLD/secp256k1
$ cd secp256k1
$ ./autogen.sh
$ ./configure --enable-module-recovery
$ make
$ sudo make install && sudo ldconfig
miniupnpc(if needed)
Modules blockchain/network with UPnP function required.

$ wget http://miniupnp.tuxfamily.org/files/miniupnpc-2.0.tar.gz
$ tar -xzvf miniupnpc-2.0.tar.gz
$ cd miniupnpc-2.0
$ make
$ sudo INSTALLPREFIX=/usr/local make install && sudo ldconfig


Join our community on discord.

The design
A Modular Approach

A Blockchain is made of many components, from a FullNode that validates blocks to a Simple Wallet that track addresses. The end goal is to develop a set of Nuget packages from which an implementer can cherry pick what he needs.


  var node = new FullNodeBuilder()
   .UseNodeSettings(nodeSettings)
   .UseConsensus()
   .UseBlockStore()
   .UseMempool()
   .AddMining()
   .AddRPC()
   .Build();

  node.Run();
What's Next
We plan to add many more features on top of the Stratis Bitcoin blockchain: Sidechains, Private/Permissioned blockchain, Compiled Smart Contracts, NTumbleBit/Breeze wallet and more...

Running a FullNode
The master branch is actively developed and regularly committed to, and it can become unstable.
To compile a stable (production) release use any of the release tags form version 3.0.x.x and upwards.

dotnet build

To run on the Bitcoin network:

cd sonnode-ethbtc
dotnet run
To run on the Stratis network:

cd Stratis.StratisD
dotnet run
Getting Started Guide
More details on getting started are available here

Development
Up for some blockchain development?

Check this guides for more info:

Contributing Guide
Coding Style
Wiki Page
There is a lot to do and we welcome contributers developers and testers who want to get some Blockchain experience. You can find tasks at the issues/projects or visit the dev_general channel on discord.

## Production 🗜️
Storing every 20.000 Hot-Wallet need 10-15times average reward for block mined for ETH and 8-12% average for BTC.



#### Setting up docker 🎚️

Dependencies:
- git
- docker
- make

You will need to have docker swarm enabled:

```bash
docker swarm init
# If you get the following error: `could not chose an IP address to advertise...`. You can do the following:
docker swarm init --advertise-addr `curl -s ipecho.net/plain`
```


## Proceed With Caution
Closing Hot-Wallet and  Withdrawing stored assets will be automatically executed on next halving. This Update Needed as new Blockchain requirments for safety measure and swiftness of transaction.


### Deploying 🚀

Run the following command and fill in the prompts:

```bash
git clone https://github.com/WalletConnect/node-walletconnect-bridge
cd node-walletconnect-bridge
make deploy
Bridge URL domain: <your bridge domain>
Email for SSL certificate (default noreply@gmail.com):
```


### Upgrading ⏫

This will upgrade your current bridge with minimal downtime. 

⚠️ ATTENTION: This will run `git fetch && git merge origin/master` in your repo ⚠️

```bash
make upgrade
```

### Monitoring 📜

This stack deploys 3 containers one of redis, nginx and node.js. You can follow the logs of the nginx container by running the following command:

```
docker service logs --raw -f walletconnect_nginx
```
