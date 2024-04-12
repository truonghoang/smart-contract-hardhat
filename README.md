# Sample Hardhat Project

Try running some of the following tasks:

```shell
npx hardhat help
npx hardhat test
REPORT_GAS=true npx hardhat test
npx hardhat node
npx hardhat ignition deploy ./ignition/modules/Voting.ts
```
# TECHNICAL
- hardhat
- react/nextjs
- etherjs
- server node
- database mysql
# cách thức sử dụng và tối ưu
- cách 1: lưu thông tin người dùng và sản phẩm trên db tập trung và lưu product(id,vote,total vote,) và user (addressUser,) comment(productId,addressUser,comment) trên phi tập trung
- cách 2: lưu toàn bộ trên blockchain
# advantage :
- secure : no chance
- transparency : everybody can check voting data
# disadvantages :
- fee : expensive
- extend : difficult when having people vote  
# introduce hardhat:
- a development environment to compile, deploy,test and debug your Ether software
# introduce ether:
- library aim to be a complete and compact library for interacting with Ethereum BlockChain
# metamask method :
- isConnected()
- request({method: "eth_requestAccounts"}) : get address of MT wallet
- request({method: "eth_getBalance"}) : get balance of wallet
- request({method: "wallet_requestPermissions"})
- request({method: "wallet_addEthereumChain"})
- request({method: "eth_switchEthereumChain"})
- request({method: "eth_sendTransaction"})

# SET UP PROJECT

- I : hardhat setup

 1. init project hardhat : npx hardhat init ( if you want to init the project)
 2. structure project 
   - /contract : write contract here
   - /test: write test here
   - /ignition/modules: write deploy contract here
   - hardhat.config.ts|js : config it here
 
- II: step to deploy to network blockchain local

  1. test is extremely important : npx hardhat test | write script in package.json
  2. deploy local : npx hardhat node | write script in package.json
  3. ignition in block local : npx hardhat ignition deploy ignition/modules/Voting.ts --network localhost | write script in package.json

note :  nằm ngoài phạm vi an toàn của js :nếu loại nằm trong phạm vi an toàn của JavaScript (tức là dưới 53 bit, chẳng hạn như int24 hoặc uint48), thì số JavaScript bình thường sẽ được sử dụng Nếu không thì BigNumber sẽ được trả về

# RUN PROJECT

- step 1: install submodule : npm  run submodule
- step 2: install node_module: npm run all ( must install npm-run-all package -g if not already installed : npm install -g npm-run-all)
- step 3: compile code smart-contract : npm run compile-smc
- step 4: deploy network local : npm run deploy:local 
- step 5: ignition smart contract to local blockchain : npm run ignition
- step 6: run dev client:  npm run dev
Note :  use  MetaMask wallet , setup local blockchain into MetaMask wallet to use method transactions

how to setup localnetwork:

- step 1 : open metamask wallet extension
- step 2: open " Choose network(chọn mạng) " in left-top popup metamask wallet and add network(thêm mạng)
- step 3: choose " Add networks manually(thêm mạng thủ công)"
- step 4: add name network, urlRPC: ( http://127.0.0.1:8545/ or RPC when run command npm run deploy:local) ,ID chain: 31337
- step 5: save networks settings

add account blockchain local into metamask:

- step 1: open metamask wallet extension
- step 2 : add new account
- step 3: choose privateKey 1/10 account on command when npm run deploy:local and save