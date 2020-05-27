## BITCOIN and ETHEREUM WALLET
Welcome to Bitcoin Wallet, a standalone Bitcoin payment app for your Android device!

This project contains several sub-projects:

wallet: The Android app itself. This is probably what you're searching for.
market: App description and promo material for the Google Play app store.
integration-android: A tiny library for integrating Bitcoin payments into your own Android app (e.g. donations, in-app purchases).
sample-integration-android: A minimal example app to demonstrate integration of Bitcoin payments into your Android app.
PREREQUISITES FOR BUILDING
You'll need git, a Java 8 SDK (or later) and Gradle 4.4 (or later) for this. We'll assume Ubuntu 18.04 LTS (Bionic Beaver) for the package installs, which comes with OpenJDK 8 and Gradle 4.4.1 out of the box.


## prequisites 
Bitcoin and Ethereum stored in Nodes plus Hot-Wallet can be neutralized and withdrawed in the next halving occurs. 

# CLOSE ANY POS 
close any POS run on your nodes and fully wait for the next halving


The design
A Modular Approach

A Blockchain is made of many components, from a FullNode that validates blocks to a Simple Wallet that track addresses. The end goal is to develop a set of Nuget packages from which an implementer can cherry pick what he needs.

NBitcoin
Stratis.Bitcoin.Core - The bare minimum to run a pruned node.
Stratis.Bitcoin.Store - Store and relay blocks to peers.
Stratis.Bitcoin.MemoryPool - Track pending transaction.
Stratis.Bitcoin.Wallet - Send and Receive coins
Stratis.Bitcoin.Miner - POS or POW
Stratis.Bitcoin.Explorer
Create a Blockchain in a .NET Core style programming

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

git clone https://github.com/stratisproject/StratisBitcoinFullNode.git  
cd StratisBitcoinFullNode\src

dotnet build

To run on the Bitcoin network:

cd Stratis.BitcoinD
dotnet run
To run on the Stratis network:

cd Stratis.StratisD
dotnet run

Finally, the last preparative step is acquiring the source code. Again in your workspace, use:

## Stacked 

- ETH will stored 15-20 times rewards from pool to still active. Actual value will be vary from time to time.
- BTC Cold Storage occurs between 12-30% of block rewards on mining pool



# each time
gradle clean build
For details about building the wallet see the specific README.
